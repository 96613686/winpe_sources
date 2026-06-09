# HrCreateLibTiffImgFromBitmap(IWICBitmapSource *,uchar * *,uint *,_LARGE_INTEGER *)

- ea: `0x1800bb9bc`
- end: `0x1800bbeb6`
- name: `?HrCreateLibTiffImgFromBitmap@@YAJPEAUIWICBitmapSource@@PEAPEAEPEAIPEAT_LARGE_INTEGER@@@Z`
- size: `1274`
- prototype: `__int64 __fastcall(struct IWICBitmapSource *, unsigned __int8 **, unsigned int *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1801b9330`

## callees

- `0x18002ae20`
- `0x18002ae60`
- `0x180031b78`
- `0x180039480`
- `0x18008fd04`
- `0x1800961e0`
- `0x1800965b0`
- `0x18009c620`
- `0x1800bb9bc`
- `0x1800bd9d4`
- `0x1800e5a18`
- `0x18017e438`
- `0x1801ae5b0`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800bbd88`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800bbd88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bba30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bbd46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bba30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bbd46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bba56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbd57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bba56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbd57`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800bba9c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800bba9c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800bbd35`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800bbd35`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800bbd0e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800bbd0e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800bbdca`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800bbdca`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800bbdf1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800bbdf1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800bba41`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800bba41`

## pseudocode

```c
__int64 __fastcall HrCreateLibTiffImgFromBitmap(
        struct IWICBitmapSource *a1,
        unsigned __int8 **a2,
        unsigned int *a3,
        union _LARGE_INTEGER *a4)
{
  CMILCOMBase *v8; // rdi
  struct IWICComponentFactory *v9; // r12
  HGLOBAL v10; // rax
  signed int LastError; // eax
  signed int v12; // ebx
  HRESULT v13; // eax
  bool v14; // zf
  int v15; // ecx
  CLibTiffEncoder *v16; // rax
  CMILCOMBase *v17; // rax
  struct IWICBitmapSourceVtbl *lpVtbl; // rax
  struct IWICBitmapSourceVtbl *v19; // rax
  int CodecFactory; // eax
  struct IWICPalette *v21; // rdx
  struct IWICBitmapFrameEncode *v22; // rax
  HGLOBAL v23; // rsi
  HGLOBAL v24; // rcx
  ULONGLONG v25; // r14
  const void *v26; // r15
  signed int v27; // eax
  bool v28; // zf
  unsigned __int8 *v29; // rax
  unsigned __int8 *v30; // rsi
  struct IWICBitmapFrameEncode *v32; // [rsp+20h] [rbp-49h] BYREF
  struct IWICPalette *v33; // [rsp+28h] [rbp-41h] BYREF
  unsigned int v34; // [rsp+30h] [rbp-39h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-31h] BYREF
  struct IWICBitmapSource *v36; // [rsp+40h] [rbp-29h] BYREF
  double v37; // [rsp+48h] [rbp-21h] BYREF
  double v38; // [rsp+50h] [rbp-19h] BYREF
  struct IWICComponentFactory *v39; // [rsp+58h] [rbp-11h] BYREF
  HGLOBAL hMem; // [rsp+60h] [rbp-9h]
  unsigned int v41; // [rsp+D0h] [rbp+67h] BYREF

  if ( !a1 || !a2 || !a3 || !a4 )
    return 2147942487LL;
  *a3 = 0;
  a4->QuadPart = 0;
  v8 = 0;
  *a2 = 0;
  v9 = 0;
  ppstm = 0;
  v32 = 0;
  v36 = 0;
  v39 = 0;
  v33 = 0;
  SetLastError(0);
  v10 = GlobalAlloc(2u, 0);
  hMem = v10;
  if ( !v10 )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2003292268;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v12);
    goto LABEL_62;
  }
  v13 = CreateStreamOnHGlobal(v10, 0, &ppstm);
  v12 = v13;
  if ( v13 < 0 )
  {
    v14 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_14;
  }
  v16 = (CLibTiffEncoder *)operator new(0xD8u);
  if ( v16 && (v17 = CLibTiffEncoder::CLibTiffEncoder(v16), (v8 = v17) != 0) )
  {
    CMILCOMBase::InternalAddRef(v17);
    v13 = CEncoderBase::Initialize((CMILCOMBase *)((char *)v8 + 136), ppstm, WICBitmapEncoderNoCache);
    v12 = v13;
    if ( v13 < 0 )
      goto LABEL_19;
    v13 = CEncoderBase::CreateNewFrame((CMILCOMBase *)((char *)v8 + 136), &v32, 0);
    v12 = v13;
    if ( v13 < 0 )
      goto LABEL_19;
    v13 = ((__int64 (__fastcall *)(struct IWICBitmapFrameEncode *, _QWORD))v32->lpVtbl->Initialize)(v32, 0);
    v12 = v13;
    if ( v13 < 0 )
      goto LABEL_19;
    lpVtbl = a1->lpVtbl;
    v34 = 0;
    v41 = 0;
    v13 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))lpVtbl->GetSize)(
            a1,
            &v34,
            &v41);
    v12 = v13;
    if ( v13 < 0 )
      goto LABEL_19;
    v13 = ((__int64 (__fastcall *)(struct IWICBitmapFrameEncode *, _QWORD, _QWORD))v32->lpVtbl->SetSize)(v32, v34, v41);
    v12 = v13;
    if ( v13 < 0
      || (v19 = a1->lpVtbl,
          v38 = 0.0,
          v37 = 0.0,
          v13 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, double *, double *))v19->GetResolution)(
                  a1,
                  &v38,
                  &v37),
          v12 = v13,
          v13 < 0)
      || v38 != 0.0
      && v37 != 0.0
      && (v13 = ((__int64 (__fastcall *)(struct IWICBitmapFrameEncode *))v32->lpVtbl->SetResolution)(v32),
          v12 = v13,
          v13 < 0) )
    {
LABEL_19:
      v14 = (_DWORD)g_doStackCaptures == 0;
      goto LABEL_14;
    }
    CodecFactory = GetCodecFactory(&v39);
    v12 = CodecFactory;
    if ( CodecFactory < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(CodecFactory);
      v9 = v39;
      goto LABEL_61;
    }
    v9 = v39;
    v13 = ((__int64 (__fastcall *)(struct IWICComponentFactory *, struct IWICPalette **))v39->lpVtbl->CreatePalette)(
            v39,
            &v33);
    v12 = v13;
    if ( v13 < 0 )
    {
LABEL_33:
      v14 = (_DWORD)g_doStackCaptures == 0;
LABEL_14:
      if ( !v14 )
      {
        v15 = v13;
LABEL_60:
        DoStackCapture(v15);
        goto LABEL_61;
      }
      goto LABEL_61;
    }
    v13 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct IWICPalette *))a1->lpVtbl->CopyPalette)(a1, v33);
    v12 = v13;
    if ( v13 == -2003292347 )
    {
      v21 = v33;
      if ( v33 )
      {
        ((void (__fastcall *)(struct IWICPalette *))v33->lpVtbl->Release)(v33);
        v21 = 0;
        v33 = 0;
      }
    }
    else
    {
      if ( v13 < 0 )
        goto LABEL_33;
      v21 = v33;
    }
    v13 = CFrameEncodeBase::SetEncoderFormat(a1, v21, v32, &v36);
    v12 = v13;
    if ( v13 < 0 )
      goto LABEL_33;
    v13 = ((__int64 (__fastcall *)(struct IWICBitmapFrameEncode *, struct IWICBitmapSource *, _QWORD))v32->lpVtbl->WriteSource)(
            v32,
            v36,
            0);
    v12 = v13;
    if ( v13 < 0 )
      goto LABEL_33;
    v13 = ((__int64 (__fastcall *)(struct IWICBitmapFrameEncode *))v32->lpVtbl->Commit)(v32);
    v12 = v13;
    if ( v13 < 0 )
      goto LABEL_33;
    v13 = CEncoderBase::Commit((CMILCOMBase *)((char *)v8 + 136));
    v12 = v13;
    if ( v13 < 0 )
      goto LABEL_33;
    v22 = v32;
    if ( v32 )
      v22 = v32 - 3;
    v23 = hMem;
    v24 = hMem;
    a4->QuadPart = LODWORD(v22[32].lpVtbl);
    v25 = GlobalSize(v24);
    v13 = ULongLongToUInt(v25, a3);
    v12 = v13;
    if ( v13 < 0 )
      goto LABEL_33;
    v26 = GlobalLock(v23);
    SetLastError(0);
    if ( v26 )
    {
      v29 = (unsigned __int8 *)malloc(v25);
      v30 = v29;
      if ( v29 )
      {
        v12 = 0;
        memcpy_0(v29, v26, v25);
        *a2 = v30;
      }
      else
      {
        v12 = -2147024882;
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(-2147024882);
      }
      GlobalUnlock(hMem);
      goto LABEL_61;
    }
    v27 = GetLastError();
    v12 = v27;
    if ( v27 > 0 )
      v12 = (unsigned __int16)v27 | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2003292268;
    v28 = (_DWORD)g_doStackCaptures == 0;
  }
  else
  {
    v28 = (_DWORD)g_doStackCaptures == 0;
    v12 = -2147024882;
  }
  if ( !v28 )
  {
    v15 = v12;
    goto LABEL_60;
  }
LABEL_61:
  GlobalFree(hMem);
LABEL_62:
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  if ( v36 )
  {
    ((void (__fastcall *)(struct IWICBitmapSource *))v36->lpVtbl->Release)(v36);
    v36 = 0;
  }
  if ( v9 )
    ((void (__fastcall *)(struct IWICComponentFactory *))v9->lpVtbl->Release)(v9);
  if ( v33 )
  {
    ((void (__fastcall *)(struct IWICPalette *))v33->lpVtbl->Release)(v33);
    v33 = 0;
  }
  if ( v32 )
  {
    ((void (__fastcall *)(struct IWICBitmapFrameEncode *))v32->lpVtbl->Release)(v32);
    v32 = 0;
  }
  if ( v8 )
    CMILCOMBase::InternalRelease(v8);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800bb9bc  push    rbp
0x1800bb9be  push    rbx
0x1800bb9bf  push    rsi
0x1800bb9c0  push    rdi
0x1800bb9c1  push    r12
0x1800bb9c3  push    r13
0x1800bb9c5  push    r14
0x1800bb9c7  push    r15
0x1800bb9c9  lea     rbp, [rsp-1Fh]
0x1800bb9ce  sub     rsp, 88h
0x1800bb9d5  xor     ebx, ebx
0x1800bb9d7  movaps  [rsp+0C0h+var_50], xmm6
0x1800bb9dc  mov     r14, r9
0x1800bb9df  mov     r15, r8
0x1800bb9e2  mov     r13, rdx
0x1800bb9e5  mov     rsi, rcx
0x1800bb9e8  test    rcx, rcx
0x1800bb9eb  jz      loc_1800BBE97
0x1800bb9f1  test    rdx, rdx
0x1800bb9f4  jz      loc_1800BBE97
0x1800bb9fa  test    r8, r8
0x1800bb9fd  jz      loc_1800BBE97
0x1800bba03  test    r9, r9
0x1800bba06  jz      loc_1800BBE97
0x1800bba0c  mov     [r8], ebx
0x1800bba0f  xor     ecx, ecx; dwErrCode
0x1800bba11  mov     [r9], rbx
0x1800bba14  mov     edi, ebx
0x1800bba16  mov     [rdx], rbx
0x1800bba19  mov     r12d, ebx
0x1800bba1c  mov     [rbp+57h+ppstm], rbx
0x1800bba20  mov     [rbp+57h+var_A0], rbx
0x1800bba24  mov     [rbp+57h+var_80], rbx
0x1800bba28  mov     [rbp+57h+var_68], rbx
0x1800bba2c  mov     [rbp+57h+var_98], rbx
0x1800bba30  call    cs:__imp_SetLastError
0x1800bba37  nop     dword ptr [rax+rax+00h]
0x1800bba3c  xor     edx, edx; dwBytes
0x1800bba3e  lea     ecx, [rbx+2]; uFlags
0x1800bba41  call    cs:__imp_GlobalAlloc
0x1800bba48  nop     dword ptr [rax+rax+00h]
0x1800bba4d  mov     [rbp+57h+hMem], rax
0x1800bba51  test    rax, rax
0x1800bba54  jnz     short loc_1800BBA93
0x1800bba56  call    cs:__imp_GetLastError
0x1800bba5d  nop     dword ptr [rax+rax+00h]
0x1800bba62  mov     ebx, eax
0x1800bba64  test    eax, eax
0x1800bba66  jle     short loc_1800BBA71
0x1800bba68  movzx   ebx, ax
0x1800bba6b  or      ebx, 80070000h
0x1800bba71  test    ebx, ebx
0x1800bba73  mov     eax, 88982F94h
0x1800bba78  cmovns  ebx, eax
0x1800bba7b  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800bba81  jz      loc_1800BBDFD
0x1800bba87  mov     ecx, ebx; int
0x1800bba89  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800bba8e  jmp     loc_1800BBDFD
0x1800bba93  lea     r8, [rbp+57h+ppstm]; ppstm
0x1800bba97  xor     edx, edx; fDeleteOnRelease
0x1800bba99  mov     rcx, rax; hGlobal
0x1800bba9c  call    cs:__imp_CreateStreamOnHGlobal
0x1800bbaa3  nop     dword ptr [rax+rax+00h]
0x1800bbaa8  mov     ebx, eax
0x1800bbaaa  test    eax, eax
0x1800bbaac  jns     short loc_1800BBAC1
0x1800bbaae  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800bbab4  jz      loc_1800BBDED
0x1800bbaba  mov     ecx, eax
0x1800bbabc  jmp     loc_1800BBDE8
0x1800bbac1  mov     ecx, 0D8h; Size
0x1800bbac6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bbacb  test    rax, rax
0x1800bbace  jz      loc_1800BBDD8
0x1800bbad4  mov     rcx, rax; this
0x1800bbad7  call    ??0CLibTiffEncoder@@QEAA@XZ; CLibTiffEncoder::CLibTiffEncoder(void)
0x1800bbadc  mov     rdi, rax
0x1800bbadf  test    rax, rax
0x1800bbae2  jz      loc_1800BBDD8
0x1800bbae8  mov     rcx, rax; this
0x1800bbaeb  call    ?InternalAddRef@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalAddRef(void)
0x1800bbaf0  mov     rdx, [rbp+57h+ppstm]; struct IStream *
0x1800bbaf4  lea     rcx, [rdi+88h]; this
0x1800bbafb  mov     r8d, 2; enum WICBitmapEncoderCacheOption
0x1800bbb01  call    ?Initialize@CEncoderBase@@UEAAJPEAUIStream@@W4WICBitmapEncoderCacheOption@@@Z; CEncoderBase::Initialize(IStream *,WICBitmapEncoderCacheOption)
0x1800bbb06  mov     ebx, eax
0x1800bbb08  test    eax, eax
0x1800bbb0a  jns     short loc_1800BBB15
0x1800bbb0c  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bbb13  jmp     short loc_1800BBAB4
0x1800bbb15  xor     r8d, r8d; struct IPropertyBag2 **
0x1800bbb18  lea     rdx, [rbp+57h+var_A0]; struct IWICBitmapFrameEncode **
0x1800bbb1c  lea     rcx, [rdi+88h]; this
0x1800bbb23  call    ?CreateNewFrame@CEncoderBase@@UEAAJPEAPEAUIWICBitmapFrameEncode@@PEAPEAUIPropertyBag2@@@Z; CEncoderBase::CreateNewFrame(IWICBitmapFrameEncode * *,IPropertyBag2 * *)
0x1800bbb28  mov     ebx, eax
0x1800bbb2a  test    eax, eax
0x1800bbb2c  js      short loc_1800BBB0C
0x1800bbb2e  mov     rcx, [rbp+57h+var_A0]
0x1800bbb32  xor     edx, edx
0x1800bbb34  mov     rax, [rcx]
0x1800bbb37  mov     rax, [rax+18h]
0x1800bbb3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbb40  mov     ebx, eax
0x1800bbb42  test    eax, eax
0x1800bbb44  js      short loc_1800BBB0C
0x1800bbb46  mov     rax, [rsi]
0x1800bbb49  lea     r8, [rbp+57h+arg_0]
0x1800bbb4d  lea     rdx, [rbp+57h+var_90]
0x1800bbb51  mov     [rbp+57h+var_90], r12d
0x1800bbb55  mov     rcx, rsi
0x1800bbb58  mov     [rbp+57h+arg_0], r12d
0x1800bbb5c  mov     rax, [rax+18h]
0x1800bbb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbb65  mov     ebx, eax
0x1800bbb67  test    eax, eax
0x1800bbb69  js      short loc_1800BBB0C
0x1800bbb6b  mov     rcx, [rbp+57h+var_A0]
0x1800bbb6f  mov     r8d, [rbp+57h+arg_0]
0x1800bbb73  mov     edx, [rbp+57h+var_90]
0x1800bbb76  mov     rax, [rcx]
0x1800bbb79  mov     rax, [rax+20h]
0x1800bbb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbb82  mov     ebx, eax
0x1800bbb84  test    eax, eax
0x1800bbb86  js      short loc_1800BBB0C
0x1800bbb88  mov     rax, [rsi]
0x1800bbb8b  lea     r8, [rbp+57h+var_78]
0x1800bbb8f  xorps   xmm6, xmm6
0x1800bbb92  lea     rdx, [rbp+57h+var_70]
0x1800bbb96  mov     rcx, rsi
0x1800bbb99  movsd   [rbp+57h+var_70], xmm6
0x1800bbb9e  movsd   [rbp+57h+var_78], xmm6
0x1800bbba3  mov     rax, [rax+28h]
0x1800bbba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbbac  mov     ebx, eax
0x1800bbbae  test    eax, eax
0x1800bbbb0  js      loc_1800BBB0C
0x1800bbbb6  ucomisd xmm6, [rbp+57h+var_70]
0x1800bbbbb  jp      short loc_1800BBBBF
0x1800bbbbd  jz      short loc_1800BBBEC
0x1800bbbbf  ucomisd xmm6, [rbp+57h+var_78]
0x1800bbbc4  jp      short loc_1800BBBC8
0x1800bbbc6  jz      short loc_1800BBBEC
0x1800bbbc8  mov     rcx, [rbp+57h+var_A0]
0x1800bbbcc  movsd   xmm2, [rbp+57h+var_78]
0x1800bbbd1  movsd   xmm1, [rbp+57h+var_70]
0x1800bbbd6  mov     rax, [rcx]
0x1800bbbd9  mov     rax, [rax+28h]
0x1800bbbdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbbe2  mov     ebx, eax
0x1800bbbe4  test    eax, eax
0x1800bbbe6  js      loc_1800BBB0C
0x1800bbbec  lea     rcx, [rbp+57h+var_68]; struct IWICComponentFactory **
0x1800bbbf0  call    ?GetCodecFactory@@YAJPEAPEAUIWICComponentFactory@@@Z; GetCodecFactory(IWICComponentFactory * *)
0x1800bbbf5  mov     ebx, eax
0x1800bbbf7  test    eax, eax
0x1800bbbf9  jns     short loc_1800BBC14
0x1800bbbfb  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bbc02  jz      short loc_1800BBC0B
0x1800bbc04  mov     ecx, eax; int
0x1800bbc06  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800bbc0b  mov     r12, [rbp+57h+var_68]
0x1800bbc0f  jmp     loc_1800BBDED
0x1800bbc14  mov     r12, [rbp+57h+var_68]
0x1800bbc18  lea     rdx, [rbp+57h+var_98]
0x1800bbc1c  mov     rcx, r12
0x1800bbc1f  mov     rax, [r12]
0x1800bbc23  mov     rax, [rax+48h]
0x1800bbc27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbc2c  mov     ebx, eax
0x1800bbc2e  test    eax, eax
0x1800bbc30  jns     short loc_1800BBC3E
0x1800bbc32  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800bbc39  jmp     loc_1800BBAB4
0x1800bbc3e  mov     rax, [rsi]
0x1800bbc41  mov     rcx, rsi
0x1800bbc44  mov     rdx, [rbp+57h+var_98]
0x1800bbc48  mov     rax, [rax+30h]
0x1800bbc4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbc51  mov     ebx, eax
0x1800bbc53  cmp     eax, 88982F45h
0x1800bbc58  jz      short loc_1800BBC64
0x1800bbc5a  test    eax, eax
0x1800bbc5c  js      short loc_1800BBC32
0x1800bbc5e  mov     rdx, [rbp+57h+var_98]
0x1800bbc62  jmp     short loc_1800BBC82
0x1800bbc64  mov     rdx, [rbp+57h+var_98]
0x1800bbc68  test    rdx, rdx
0x1800bbc6b  jz      short loc_1800BBC82
0x1800bbc6d  mov     rax, [rdx]
0x1800bbc70  mov     rcx, rdx
0x1800bbc73  mov     rax, [rax+10h]
0x1800bbc77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbc7c  xor     edx, edx; struct IWICPalette *
0x1800bbc7e  mov     [rbp+57h+var_98], rdx
0x1800bbc82  mov     r8, [rbp+57h+var_A0]; struct IWICBitmapFrameEncode *
0x1800bbc86  lea     r9, [rbp+57h+var_80]; struct IWICBitmapSource **
0x1800bbc8a  mov     rcx, rsi; struct IWICBitmapSource *
0x1800bbc8d  call    ?SetEncoderFormat@CFrameEncodeBase@@SAJPEAUIWICBitmapSource@@PEAUIWICPalette@@PEAUIWICBitmapFrameEncode@@PEAPEAU2@@Z; CFrameEncodeBase::SetEncoderFormat(IWICBitmapSource *,IWICPalette *,IWICBitmapFrameEncode *,IWICBitmapSource * *)
0x1800bbc92  mov     ebx, eax
0x1800bbc94  test    eax, eax
0x1800bbc96  js      short loc_1800BBC32
0x1800bbc98  mov     rcx, [rbp+57h+var_A0]
0x1800bbc9c  xor     r8d, r8d
0x1800bbc9f  mov     rdx, [rbp+57h+var_80]
0x1800bbca3  mov     rax, [rcx]
0x1800bbca6  mov     rax, [rax+58h]
0x1800bbcaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbcaf  mov     ebx, eax
0x1800bbcb1  test    eax, eax
0x1800bbcb3  js      loc_1800BBC32
0x1800bbcb9  mov     rcx, [rbp+57h+var_A0]
0x1800bbcbd  mov     rax, [rcx]
0x1800bbcc0  mov     rax, [rax+60h]
0x1800bbcc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbcc9  mov     ebx, eax
0x1800bbccb  test    eax, eax
0x1800bbccd  js      loc_1800BBC32
0x1800bbcd3  lea     rcx, [rdi+88h]; this
0x1800bbcda  call    ?Commit@CEncoderBase@@UEAAJXZ; CEncoderBase::Commit(void)
0x1800bbcdf  mov     ebx, eax
0x1800bbce1  test    eax, eax
0x1800bbce3  js      loc_1800BBC32
0x1800bbce9  mov     rax, [rbp+57h+var_A0]
0x1800bbced  test    rax, rax
0x1800bbcf0  jz      short loc_1800BBCF6
0x1800bbcf2  add     rax, 0FFFFFFFFFFFFFFE8h
0x1800bbcf6  mov     eax, [rax+100h]
0x1800bbcfc  mov     rsi, [rbp+57h+hMem]
0x1800bbd00  mov     rcx, rsi; hMem
0x1800bbd03  mov     [r14], eax
0x1800bbd06  mov     dword ptr [r14+4], 0
0x1800bbd0e  call    cs:__imp_GlobalSize
0x1800bbd15  nop     dword ptr [rax+rax+00h]
0x1800bbd1a  mov     rcx, rax; ullOperand
0x1800bbd1d  mov     rdx, r15; puResult
0x1800bbd20  mov     r14, rax
0x1800bbd23  call    ULongLongToUInt
0x1800bbd28  mov     ebx, eax
0x1800bbd2a  test    eax, eax
0x1800bbd2c  js      loc_1800BBC32
0x1800bbd32  mov     rcx, rsi; hMem
0x1800bbd35  call    cs:__imp_GlobalLock
0x1800bbd3c  nop     dword ptr [rax+rax+00h]
0x1800bbd41  xor     ecx, ecx; dwErrCode
0x1800bbd43  mov     r15, rax
0x1800bbd46  call    cs:__imp_SetLastError
0x1800bbd4d  nop     dword ptr [rax+rax+00h]
0x1800bbd52  test    r15, r15
0x1800bbd55  jnz     short loc_1800BBD85
0x1800bbd57  call    cs:__imp_GetLastError
0x1800bbd5e  nop     dword ptr [rax+rax+00h]
0x1800bbd63  mov     ebx, eax
0x1800bbd65  test    eax, eax
0x1800bbd67  jle     short loc_1800BBD72
0x1800bbd69  movzx   ebx, ax
0x1800bbd6c  or      ebx, 80070000h
0x1800bbd72  test    ebx, ebx
0x1800bbd74  mov     eax, 88982F94h
0x1800bbd79  cmovns  ebx, eax
0x1800bbd7c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800bbd83  jmp     short loc_1800BBDE4
0x1800bbd85  mov     rcx, r14; Size
0x1800bbd88  call    cs:__imp_malloc
0x1800bbd8f  nop     dword ptr [rax+rax+00h]
0x1800bbd94  mov     rsi, rax
0x1800bbd97  test    rax, rax
0x1800bbd9a  jnz     short loc_1800BBDB2
0x1800bbd9c  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800bbda2  mov     ebx, 8007000Eh
0x1800bbda7  jz      short loc_1800BBDC6
0x1800bbda9  mov     ecx, ebx; int
0x1800bbdab  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800bbdb0  jmp     short loc_1800BBDC6
0x1800bbdb2  xor     ebx, ebx
0x1800bbdb4  mov     r8, r14; Size
0x1800bbdb7  mov     rdx, r15; Src
0x1800bbdba  mov     rcx, rsi; void *
0x1800bbdbd  call    memcpy_0
0x1800bbdc2  mov     [r13+0], rsi
0x1800bbdc6  mov     rcx, [rbp+57h+hMem]; hMem
0x1800bbdca  call    cs:__imp_GlobalUnlock
0x1800bbdd1  nop     dword ptr [rax+rax+00h]
0x1800bbdd6  jmp     short loc_1800BBDED
0x1800bbdd8  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800bbddf  mov     ebx, 8007000Eh
0x1800bbde4  jz      short loc_1800BBDED
0x1800bbde6  mov     ecx, ebx; int
0x1800bbde8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800bbded  mov     rcx, [rbp+57h+hMem]; hMem
0x1800bbdf1  call    cs:__imp_GlobalFree
0x1800bbdf8  nop     dword ptr [rax+rax+00h]
0x1800bbdfd  mov     rcx, [rbp+57h+ppstm]
0x1800bbe01  test    rcx, rcx
0x1800bbe04  jz      short loc_1800BBE1A
0x1800bbe06  mov     rax, [rcx]
0x1800bbe09  mov     rax, [rax+10h]
0x1800bbe0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbe12  mov     [rbp+57h+ppstm], 0
  ... truncated ...
```
