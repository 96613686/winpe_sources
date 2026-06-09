# ConvertIWICBitmapSourceTo32bppHBITMAP(IWICBitmapSource *,IWICImagingFactory *,HBITMAP__ * *)

- ea: `0x18002c9f0`
- end: `0x18002cc38`
- name: `?ConvertIWICBitmapSourceTo32bppHBITMAP@@YAJPEAUIWICBitmapSource@@PEAUIWICImagingFactory@@PEAPEAUHBITMAP__@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(struct IWICBitmapSource *, struct IWICImagingFactory *, HBITMAP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800072e0`

## callees

- `0x180004c98`
- `0x18002c9f0`
- `0x180043c30`
- `0x180046f62`
- `0x180072010`

## import_xrefs

- `GDI32!DeleteObject` at `0x18002cc1f`
- `GDI32!DeleteObject` at `0x18002cc1f`
- `GDI32!CreateDIBSection` at `0x18002cb63`
- `GDI32!CreateDIBSection` at `0x18002cb63`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ConvertIWICBitmapSourceTo32bppHBITMAP(
        struct IWICBitmapSource *a1,
        struct IWICImagingFactory *a2,
        HBITMAP *a3)
{
  int v6; // ebx
  HRESULT (__stdcall *CreateFormatConverter)(IWICImagingFactory *, IWICFormatConverter **); // rbx
  struct IWICBitmapSource *v8; // rcx
  struct IWICBitmapSource *v9; // rdi
  HBITMAP v10; // rsi
  struct IWICBitmapSource *v11; // rcx
  struct IWICBitmapSource *v13; // [rsp+40h] [rbp-49h] BYREF
  LONG v14; // [rsp+48h] [rbp-41h] BYREF
  struct IWICBitmapSource *v15; // [rsp+50h] [rbp-39h]
  GUID Buf2; // [rsp+60h] [rbp-29h] BYREF
  __int128 Buf1; // [rsp+70h] [rbp-19h] BYREF
  BITMAPINFO pbmi; // [rsp+80h] [rbp-9h] BYREF

  *a3 = 0;
  Buf2 = GUID_WICPixelFormat32bppBGRA;
  v15 = 0;
  Buf1 = 0;
  v6 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int128 *))a1->lpVtbl->GetPixelFormat)(a1, &Buf1);
  if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
  {
    v15 = a1;
    ((void (__fastcall *)(struct IWICBitmapSource *))a1->lpVtbl->AddRef)(a1);
  }
  else
  {
    v13 = 0;
    CreateFormatConverter = a2->lpVtbl->CreateFormatConverter;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v13);
    v6 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, struct IWICBitmapSource **))CreateFormatConverter)(
           a2,
           &v13);
    if ( v6 >= 0
      && (v6 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICBitmapSource *, GUID *, _QWORD, _QWORD, _QWORD, _DWORD))v13->lpVtbl[1].QueryInterface)(
                 v13,
                 a1,
                 &Buf2,
                 0,
                 0,
                 0,
                 0),
          v6 >= 0) )
    {
      v8 = 0;
      v15 = v13;
    }
    else
    {
      v8 = v13;
    }
    if ( v8 )
    {
      v13 = 0;
      ((void (__fastcall *)(struct IWICBitmapSource *))v8->lpVtbl->Release)(v8);
    }
  }
  if ( v6 >= 0 )
  {
    v9 = v15;
    *a3 = 0;
    v14 = 0;
    LODWORD(v13) = 0;
    v6 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, LONG *, struct IWICBitmapSource **))v9->lpVtbl->GetSize)(
           v9,
           &v14,
           &v13);
    if ( v6 >= 0 )
    {
      memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
      pbmi.bmiHeader.biSize = 40;
      pbmi.bmiHeader.biWidth = v14;
      pbmi.bmiHeader.biHeight = -(int)v13;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      *(_QWORD *)&Buf2.Data1 = 0;
      v10 = CreateDIBSection(0, &pbmi, 0, (void **)&Buf2, 0, 0);
      if ( v10 )
      {
        *(_QWORD *)&Buf1 = 0;
        *((_QWORD *)&Buf1 + 1) = __PAIR64__((unsigned int)v13, v14);
        v6 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int128 *, _QWORD, _QWORD, _QWORD))v9->lpVtbl->CopyPixels)(
               v9,
               &Buf1,
               (unsigned int)(4 * v14),
               (unsigned int)(4 * v14 * (_DWORD)v13),
               *(_QWORD *)&Buf2.Data1);
        if ( v6 < 0 )
          DeleteObject(v10);
        else
          *a3 = v10;
      }
      else
      {
        v6 = -2147024882;
      }
    }
  }
  v11 = v15;
  if ( v15 )
  {
    v15 = 0;
    ((void (__fastcall *)(struct IWICBitmapSource *))v11->lpVtbl->Release)(v11);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002c9f0  mov     [rsp-8+arg_18], rbx
0x18002c9f5  push    rbp
0x18002c9f6  push    rsi
0x18002c9f7  push    rdi
0x18002c9f8  push    r14
0x18002c9fa  push    r15
0x18002c9fc  lea     rbp, [rsp-37h]
0x18002ca01  sub     rsp, 0C0h
0x18002ca08  mov     rax, cs:__security_cookie
0x18002ca0f  xor     rax, rsp
0x18002ca12  mov     [rbp+57h+var_30], rax
0x18002ca16  mov     r14, r8
0x18002ca19  mov     rsi, rdx
0x18002ca1c  mov     rdi, rcx
0x18002ca1f  xor     r15d, r15d
0x18002ca22  mov     [r8], r15
0x18002ca25  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x18002ca2c  movaps  [rbp+57h+Buf2], xmm0
0x18002ca30  mov     [rbp+57h+var_90], r15
0x18002ca34  xorps   xmm0, xmm0
0x18002ca37  movups  [rbp+57h+Buf1], xmm0
0x18002ca3b  mov     rax, [rcx]
0x18002ca3e  lea     rdx, [rbp+57h+Buf1]
0x18002ca42  mov     rax, [rax+20h]
0x18002ca46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca4b  mov     ebx, eax
0x18002ca4d  mov     r8d, 10h; Size
0x18002ca53  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18002ca57  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18002ca5b  call    memcmp_0
0x18002ca60  test    eax, eax
0x18002ca62  jz      loc_18002CBFD
0x18002ca68  mov     [rbp+57h+var_A0], r15
0x18002ca6c  mov     rax, [rsi]
0x18002ca6f  mov     rbx, [rax+50h]
0x18002ca73  lea     rcx, [rbp+57h+var_A0]
0x18002ca77  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002ca7c  lea     rdx, [rbp+57h+var_A0]
0x18002ca80  mov     rcx, rsi
0x18002ca83  mov     rax, rbx
0x18002ca86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca8b  mov     ebx, eax
0x18002ca8d  test    eax, eax
0x18002ca8f  js      short loc_18002CAC8
0x18002ca91  mov     rcx, [rbp+57h+var_A0]
0x18002ca95  mov     rax, [rcx]
0x18002ca98  mov     [rsp+0E0h+var_B0], r15d
0x18002ca9d  xorps   xmm0, xmm0
0x18002caa0  movsd   qword ptr [rsp+0E0h+offset], xmm0
0x18002caa6  mov     [rsp+0E0h+hSection], r15
0x18002caab  xor     r9d, r9d
0x18002caae  lea     r8, [rbp+57h+Buf2]
0x18002cab2  mov     rdx, rdi
0x18002cab5  mov     rax, [rax+40h]
0x18002cab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cabe  mov     ebx, eax
0x18002cac0  test    eax, eax
0x18002cac2  jns     loc_18002CC27
0x18002cac8  mov     rcx, [rbp+57h+var_A0]
0x18002cacc  test    rcx, rcx
0x18002cacf  jz      short loc_18002CAE2
0x18002cad1  mov     [rbp+57h+var_A0], r15
0x18002cad5  mov     rax, [rcx]
0x18002cad8  mov     rax, [rax+10h]
0x18002cadc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cae1  nop
0x18002cae2  test    ebx, ebx
0x18002cae4  js      loc_18002CBBE
0x18002caea  mov     rdi, [rbp+57h+var_90]
0x18002caee  mov     [r14], r15
0x18002caf1  mov     [rbp+57h+var_98], r15d
0x18002caf5  mov     dword ptr [rbp+57h+var_A0], r15d
0x18002caf9  mov     rax, [rdi]
0x18002cafc  lea     r8, [rbp+57h+var_A0]
0x18002cb00  lea     rdx, [rbp+57h+var_98]
0x18002cb04  mov     rcx, rdi
0x18002cb07  mov     rax, [rax+18h]
0x18002cb0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb10  mov     ebx, eax
0x18002cb12  test    eax, eax
0x18002cb14  js      loc_18002CBBE
0x18002cb1a  xorps   xmm0, xmm0
0x18002cb1d  xor     eax, eax
0x18002cb1f  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x18002cb23  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x18002cb27  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x18002cb2b  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x18002cb32  mov     eax, [rbp+57h+var_98]
0x18002cb35  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x18002cb38  mov     eax, dword ptr [rbp+57h+var_A0]
0x18002cb3b  neg     eax
0x18002cb3d  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x18002cb40  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x18002cb48  mov     qword ptr [rbp+57h+Buf2], r15
0x18002cb4c  mov     [rsp+0E0h+offset], r15d; offset
0x18002cb51  mov     [rsp+0E0h+hSection], r15; hSection
0x18002cb56  lea     r9, [rbp+57h+Buf2]; ppvBits
0x18002cb5a  xor     r8d, r8d; usage
0x18002cb5d  lea     rdx, [rbp+57h+pbmi]; pbmi
0x18002cb61  xor     ecx, ecx; hdc
0x18002cb63  call    cs:__imp_CreateDIBSection
0x18002cb69  mov     rsi, rax
0x18002cb6c  test    rax, rax
0x18002cb6f  jz      loc_18002CC15
0x18002cb75  mov     qword ptr [rbp+57h+Buf1], r15
0x18002cb79  mov     r8d, [rbp+57h+var_98]
0x18002cb7d  mov     dword ptr [rbp+57h+Buf1+8], r8d
0x18002cb81  mov     r9d, dword ptr [rbp+57h+var_A0]
0x18002cb85  mov     dword ptr [rbp+57h+Buf1+0Ch], r9d
0x18002cb89  mov     rdx, [rdi]
0x18002cb8c  imul    r9d, r8d
0x18002cb90  shl     r9d, 2
0x18002cb94  lea     r8d, ds:0[r8*4]
0x18002cb9c  mov     rax, [rdx+38h]
0x18002cba0  mov     rdx, qword ptr [rbp+57h+Buf2]
0x18002cba4  mov     [rsp+0E0h+hSection], rdx
0x18002cba9  lea     rdx, [rbp+57h+Buf1]
0x18002cbad  mov     rcx, rdi
0x18002cbb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbb5  mov     ebx, eax
0x18002cbb7  test    eax, eax
0x18002cbb9  js      short loc_18002CC1C
0x18002cbbb  mov     [r14], rsi
0x18002cbbe  mov     rcx, [rbp+57h+var_90]
0x18002cbc2  test    rcx, rcx
0x18002cbc5  jz      short loc_18002CBD8
0x18002cbc7  mov     [rbp+57h+var_90], r15
0x18002cbcb  mov     rdx, [rcx]
0x18002cbce  mov     rax, [rdx+10h]
0x18002cbd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbd7  nop
0x18002cbd8  mov     eax, ebx
0x18002cbda  mov     rcx, [rbp+57h+var_30]
0x18002cbde  xor     rcx, rsp; StackCookie
0x18002cbe1  call    __security_check_cookie
0x18002cbe6  mov     rbx, [rsp+0E0h+arg_18]
0x18002cbee  add     rsp, 0C0h
0x18002cbf5  pop     r15
0x18002cbf7  pop     r14
0x18002cbf9  pop     rdi
0x18002cbfa  pop     rsi
0x18002cbfb  pop     rbp
0x18002cbfc  retn
0x18002cbfd  mov     [rbp+57h+var_90], rdi
0x18002cc01  mov     rax, [rdi]
0x18002cc04  mov     rcx, rdi
0x18002cc07  mov     rax, [rax+8]
0x18002cc0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc10  jmp     loc_18002CAE2
0x18002cc15  mov     ebx, 8007000Eh
0x18002cc1a  jmp     short loc_18002CBBE
0x18002cc1c  mov     rcx, rsi; ho
0x18002cc1f  call    cs:__imp_DeleteObject
0x18002cc25  jmp     short loc_18002CBBE
0x18002cc27  mov     rax, [rbp+57h+var_A0]
0x18002cc2b  mov     rcx, r15
0x18002cc2e  mov     [rbp+57h+var_90], rax
0x18002cc32  jmp     loc_18002CACC
```
