# HrCreateLibTiffImgFromBitmap(IWICBitmapSource *,uchar * *,uint *,_LARGE_INTEGER *)

- ea: `0x1800b97f4`
- end: `0x1800b9cab`
- name: `?HrCreateLibTiffImgFromBitmap@@YAJPEAUIWICBitmapSource@@PEAPEAEPEAIPEAT_LARGE_INTEGER@@@Z`
- size: `1207`
- prototype: `__int64 __fastcall(struct IWICBitmapSource *, unsigned __int8 **, unsigned int *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1801b5b90`

## callees

- `0x18003b2f0`
- `0x18003b320`
- `0x1800402f4`
- `0x18006ac40`
- `0x18008e0b4`
- `0x180094b30`
- `0x180094dc0`
- `0x18009ac20`
- `0x1800b97f4`
- `0x1800bb784`
- `0x1800e2b48`
- `0x18017b528`
- `0x1801ab03c`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b9b90`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b9b90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b9868`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b9b5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b9868`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b9b5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9b65`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800b98c2`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800b98c2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800b9b4f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800b9b4f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800b9b2e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800b9b2e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800b9bcc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800b9bcc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b9bed`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b9bed`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800b9873`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800b9873`

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
  SIZE_T v25; // r14
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
0x1800b97f4  push    rbp
0x1800b97f6  push    rbx
0x1800b97f7  push    rsi
0x1800b97f8  push    rdi
0x1800b97f9  push    r12
0x1800b97fb  push    r13
0x1800b97fd  push    r14
0x1800b97ff  push    r15
0x1800b9801  lea     rbp, [rsp-1Fh]
0x1800b9806  sub     rsp, 88h
0x1800b980d  xor     ebx, ebx
0x1800b980f  movaps  [rsp+0C0h+var_50], xmm6
0x1800b9814  mov     r14, r9
0x1800b9817  mov     r15, r8
0x1800b981a  mov     r13, rdx
0x1800b981d  mov     rsi, rcx
0x1800b9820  test    rcx, rcx
0x1800b9823  jz      loc_1800B9C8D
0x1800b9829  test    rdx, rdx
0x1800b982c  jz      loc_1800B9C8D
0x1800b9832  test    r8, r8
0x1800b9835  jz      loc_1800B9C8D
0x1800b983b  test    r9, r9
0x1800b983e  jz      loc_1800B9C8D
0x1800b9844  mov     [r8], ebx
0x1800b9847  xor     ecx, ecx; dwErrCode
0x1800b9849  mov     [r9], rbx
0x1800b984c  mov     edi, ebx
0x1800b984e  mov     [rdx], rbx
0x1800b9851  mov     r12d, ebx
0x1800b9854  mov     [rbp+57h+ppstm], rbx
0x1800b9858  mov     [rbp+57h+var_A0], rbx
0x1800b985c  mov     [rbp+57h+var_80], rbx
0x1800b9860  mov     [rbp+57h+var_68], rbx
0x1800b9864  mov     [rbp+57h+var_98], rbx
0x1800b9868  call    cs:__imp_SetLastError
0x1800b986e  xor     edx, edx; dwBytes
0x1800b9870  lea     ecx, [rbx+2]; uFlags
0x1800b9873  call    cs:__imp_GlobalAlloc
0x1800b9879  mov     [rbp+57h+hMem], rax
0x1800b987d  test    rax, rax
0x1800b9880  jnz     short loc_1800B98B9
0x1800b9882  call    cs:__imp_GetLastError
0x1800b9888  mov     ebx, eax
0x1800b988a  test    eax, eax
0x1800b988c  jle     short loc_1800B9897
0x1800b988e  movzx   ebx, ax
0x1800b9891  or      ebx, 80070000h
0x1800b9897  test    ebx, ebx
0x1800b9899  mov     eax, 88982F94h
0x1800b989e  cmovns  ebx, eax
0x1800b98a1  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800b98a7  jz      loc_1800B9BF3
0x1800b98ad  mov     ecx, ebx; int
0x1800b98af  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b98b4  jmp     loc_1800B9BF3
0x1800b98b9  lea     r8, [rbp+57h+ppstm]; ppstm
0x1800b98bd  xor     edx, edx; fDeleteOnRelease
0x1800b98bf  mov     rcx, rax; hGlobal
0x1800b98c2  call    cs:__imp_CreateStreamOnHGlobal
0x1800b98c8  mov     ebx, eax
0x1800b98ca  test    eax, eax
0x1800b98cc  jns     short loc_1800B98E1
0x1800b98ce  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800b98d4  jz      loc_1800B9BE9
0x1800b98da  mov     ecx, eax
0x1800b98dc  jmp     loc_1800B9BE4
0x1800b98e1  mov     ecx, 0D8h; Size
0x1800b98e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b98eb  test    rax, rax
0x1800b98ee  jz      loc_1800B9BD4
0x1800b98f4  mov     rcx, rax; this
0x1800b98f7  call    ??0CLibTiffEncoder@@QEAA@XZ; CLibTiffEncoder::CLibTiffEncoder(void)
0x1800b98fc  mov     rdi, rax
0x1800b98ff  test    rax, rax
0x1800b9902  jz      loc_1800B9BD4
0x1800b9908  mov     rcx, rax; this
0x1800b990b  call    ?InternalAddRef@CMILCOMBase@@QEAAKXZ; CMILCOMBase::InternalAddRef(void)
0x1800b9910  mov     rdx, [rbp+57h+ppstm]; struct IStream *
0x1800b9914  lea     rcx, [rdi+88h]; this
0x1800b991b  mov     r8d, 2; enum WICBitmapEncoderCacheOption
0x1800b9921  call    ?Initialize@CEncoderBase@@UEAAJPEAUIStream@@W4WICBitmapEncoderCacheOption@@@Z; CEncoderBase::Initialize(IStream *,WICBitmapEncoderCacheOption)
0x1800b9926  mov     ebx, eax
0x1800b9928  test    eax, eax
0x1800b992a  jns     short loc_1800B9935
0x1800b992c  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800b9933  jmp     short loc_1800B98D4
0x1800b9935  xor     r8d, r8d; struct IPropertyBag2 **
0x1800b9938  lea     rdx, [rbp+57h+var_A0]; struct IWICBitmapFrameEncode **
0x1800b993c  lea     rcx, [rdi+88h]; this
0x1800b9943  call    ?CreateNewFrame@CEncoderBase@@UEAAJPEAPEAUIWICBitmapFrameEncode@@PEAPEAUIPropertyBag2@@@Z; CEncoderBase::CreateNewFrame(IWICBitmapFrameEncode * *,IPropertyBag2 * *)
0x1800b9948  mov     ebx, eax
0x1800b994a  test    eax, eax
0x1800b994c  js      short loc_1800B992C
0x1800b994e  mov     rcx, [rbp+57h+var_A0]
0x1800b9952  xor     edx, edx
0x1800b9954  mov     rax, [rcx]
0x1800b9957  mov     rax, [rax+18h]
0x1800b995b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9960  mov     ebx, eax
0x1800b9962  test    eax, eax
0x1800b9964  js      short loc_1800B992C
0x1800b9966  mov     rax, [rsi]
0x1800b9969  lea     r8, [rbp+57h+arg_0]
0x1800b996d  lea     rdx, [rbp+57h+var_90]
0x1800b9971  mov     [rbp+57h+var_90], r12d
0x1800b9975  mov     rcx, rsi
0x1800b9978  mov     [rbp+57h+arg_0], r12d
0x1800b997c  mov     rax, [rax+18h]
0x1800b9980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9985  mov     ebx, eax
0x1800b9987  test    eax, eax
0x1800b9989  js      short loc_1800B992C
0x1800b998b  mov     rcx, [rbp+57h+var_A0]
0x1800b998f  mov     r8d, [rbp+57h+arg_0]
0x1800b9993  mov     edx, [rbp+57h+var_90]
0x1800b9996  mov     rax, [rcx]
0x1800b9999  mov     rax, [rax+20h]
0x1800b999d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b99a2  mov     ebx, eax
0x1800b99a4  test    eax, eax
0x1800b99a6  js      short loc_1800B992C
0x1800b99a8  mov     rax, [rsi]
0x1800b99ab  lea     r8, [rbp+57h+var_78]
0x1800b99af  xorps   xmm6, xmm6
0x1800b99b2  lea     rdx, [rbp+57h+var_70]
0x1800b99b6  mov     rcx, rsi
0x1800b99b9  movsd   [rbp+57h+var_70], xmm6
0x1800b99be  movsd   [rbp+57h+var_78], xmm6
0x1800b99c3  mov     rax, [rax+28h]
0x1800b99c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b99cc  mov     ebx, eax
0x1800b99ce  test    eax, eax
0x1800b99d0  js      loc_1800B992C
0x1800b99d6  ucomisd xmm6, [rbp+57h+var_70]
0x1800b99db  jp      short loc_1800B99DF
0x1800b99dd  jz      short loc_1800B9A0C
0x1800b99df  ucomisd xmm6, [rbp+57h+var_78]
0x1800b99e4  jp      short loc_1800B99E8
0x1800b99e6  jz      short loc_1800B9A0C
0x1800b99e8  mov     rcx, [rbp+57h+var_A0]
0x1800b99ec  movsd   xmm2, [rbp+57h+var_78]
0x1800b99f1  movsd   xmm1, [rbp+57h+var_70]
0x1800b99f6  mov     rax, [rcx]
0x1800b99f9  mov     rax, [rax+28h]
0x1800b99fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9a02  mov     ebx, eax
0x1800b9a04  test    eax, eax
0x1800b9a06  js      loc_1800B992C
0x1800b9a0c  lea     rcx, [rbp+57h+var_68]; struct IWICComponentFactory **
0x1800b9a10  call    ?GetCodecFactory@@YAJPEAPEAUIWICComponentFactory@@@Z; GetCodecFactory(IWICComponentFactory * *)
0x1800b9a15  mov     ebx, eax
0x1800b9a17  test    eax, eax
0x1800b9a19  jns     short loc_1800B9A34
0x1800b9a1b  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800b9a22  jz      short loc_1800B9A2B
0x1800b9a24  mov     ecx, eax; int
0x1800b9a26  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b9a2b  mov     r12, [rbp+57h+var_68]
0x1800b9a2f  jmp     loc_1800B9BE9
0x1800b9a34  mov     r12, [rbp+57h+var_68]
0x1800b9a38  lea     rdx, [rbp+57h+var_98]
0x1800b9a3c  mov     rcx, r12
0x1800b9a3f  mov     rax, [r12]
0x1800b9a43  mov     rax, [rax+48h]
0x1800b9a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9a4c  mov     ebx, eax
0x1800b9a4e  test    eax, eax
0x1800b9a50  jns     short loc_1800B9A5E
0x1800b9a52  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800b9a59  jmp     loc_1800B98D4
0x1800b9a5e  mov     rax, [rsi]
0x1800b9a61  mov     rcx, rsi
0x1800b9a64  mov     rdx, [rbp+57h+var_98]
0x1800b9a68  mov     rax, [rax+30h]
0x1800b9a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9a71  mov     ebx, eax
0x1800b9a73  cmp     eax, 88982F45h
0x1800b9a78  jz      short loc_1800B9A84
0x1800b9a7a  test    eax, eax
0x1800b9a7c  js      short loc_1800B9A52
0x1800b9a7e  mov     rdx, [rbp+57h+var_98]
0x1800b9a82  jmp     short loc_1800B9AA2
0x1800b9a84  mov     rdx, [rbp+57h+var_98]
0x1800b9a88  test    rdx, rdx
0x1800b9a8b  jz      short loc_1800B9AA2
0x1800b9a8d  mov     rax, [rdx]
0x1800b9a90  mov     rcx, rdx
0x1800b9a93  mov     rax, [rax+10h]
0x1800b9a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9a9c  xor     edx, edx; struct IWICPalette *
0x1800b9a9e  mov     [rbp+57h+var_98], rdx
0x1800b9aa2  mov     r8, [rbp+57h+var_A0]; struct IWICBitmapFrameEncode *
0x1800b9aa6  lea     r9, [rbp+57h+var_80]; struct IWICBitmapSource **
0x1800b9aaa  mov     rcx, rsi; struct IWICBitmapSource *
0x1800b9aad  call    ?SetEncoderFormat@CFrameEncodeBase@@SAJPEAUIWICBitmapSource@@PEAUIWICPalette@@PEAUIWICBitmapFrameEncode@@PEAPEAU2@@Z; CFrameEncodeBase::SetEncoderFormat(IWICBitmapSource *,IWICPalette *,IWICBitmapFrameEncode *,IWICBitmapSource * *)
0x1800b9ab2  mov     ebx, eax
0x1800b9ab4  test    eax, eax
0x1800b9ab6  js      short loc_1800B9A52
0x1800b9ab8  mov     rcx, [rbp+57h+var_A0]
0x1800b9abc  xor     r8d, r8d
0x1800b9abf  mov     rdx, [rbp+57h+var_80]
0x1800b9ac3  mov     rax, [rcx]
0x1800b9ac6  mov     rax, [rax+58h]
0x1800b9aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9acf  mov     ebx, eax
0x1800b9ad1  test    eax, eax
0x1800b9ad3  js      loc_1800B9A52
0x1800b9ad9  mov     rcx, [rbp+57h+var_A0]
0x1800b9add  mov     rax, [rcx]
0x1800b9ae0  mov     rax, [rax+60h]
0x1800b9ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9ae9  mov     ebx, eax
0x1800b9aeb  test    eax, eax
0x1800b9aed  js      loc_1800B9A52
0x1800b9af3  lea     rcx, [rdi+88h]; this
0x1800b9afa  call    ?Commit@CEncoderBase@@UEAAJXZ; CEncoderBase::Commit(void)
0x1800b9aff  mov     ebx, eax
0x1800b9b01  test    eax, eax
0x1800b9b03  js      loc_1800B9A52
0x1800b9b09  mov     rax, [rbp+57h+var_A0]
0x1800b9b0d  test    rax, rax
0x1800b9b10  jz      short loc_1800B9B16
0x1800b9b12  add     rax, 0FFFFFFFFFFFFFFE8h
0x1800b9b16  mov     eax, [rax+100h]
0x1800b9b1c  mov     rsi, [rbp+57h+hMem]
0x1800b9b20  mov     rcx, rsi; hMem
0x1800b9b23  mov     [r14], eax
0x1800b9b26  mov     dword ptr [r14+4], 0
0x1800b9b2e  call    cs:__imp_GlobalSize
0x1800b9b34  mov     rcx, rax; ullOperand
0x1800b9b37  mov     rdx, r15; puResult
0x1800b9b3a  mov     r14, rax
0x1800b9b3d  call    ULongLongToUInt
0x1800b9b42  mov     ebx, eax
0x1800b9b44  test    eax, eax
0x1800b9b46  js      loc_1800B9A52
0x1800b9b4c  mov     rcx, rsi; hMem
0x1800b9b4f  call    cs:__imp_GlobalLock
0x1800b9b55  xor     ecx, ecx; dwErrCode
0x1800b9b57  mov     r15, rax
0x1800b9b5a  call    cs:__imp_SetLastError
0x1800b9b60  test    r15, r15
0x1800b9b63  jnz     short loc_1800B9B8D
0x1800b9b65  call    cs:__imp_GetLastError
0x1800b9b6b  mov     ebx, eax
0x1800b9b6d  test    eax, eax
0x1800b9b6f  jle     short loc_1800B9B7A
0x1800b9b71  movzx   ebx, ax
0x1800b9b74  or      ebx, 80070000h
0x1800b9b7a  test    ebx, ebx
0x1800b9b7c  mov     eax, 88982F94h
0x1800b9b81  cmovns  ebx, eax
0x1800b9b84  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800b9b8b  jmp     short loc_1800B9BE0
0x1800b9b8d  mov     rcx, r14; Size
0x1800b9b90  call    cs:__imp_malloc
0x1800b9b96  mov     rsi, rax
0x1800b9b99  test    rax, rax
0x1800b9b9c  jnz     short loc_1800B9BB4
0x1800b9b9e  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800b9ba4  mov     ebx, 8007000Eh
0x1800b9ba9  jz      short loc_1800B9BC8
0x1800b9bab  mov     ecx, ebx; int
0x1800b9bad  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b9bb2  jmp     short loc_1800B9BC8
0x1800b9bb4  xor     ebx, ebx
0x1800b9bb6  mov     r8, r14; Size
0x1800b9bb9  mov     rdx, r15; Src
0x1800b9bbc  mov     rcx, rsi; void *
0x1800b9bbf  call    memcpy_0
0x1800b9bc4  mov     [r13+0], rsi
0x1800b9bc8  mov     rcx, [rbp+57h+hMem]; hMem
0x1800b9bcc  call    cs:__imp_GlobalUnlock
0x1800b9bd2  jmp     short loc_1800B9BE9
0x1800b9bd4  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800b9bdb  mov     ebx, 8007000Eh
0x1800b9be0  jz      short loc_1800B9BE9
0x1800b9be2  mov     ecx, ebx; int
0x1800b9be4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b9be9  mov     rcx, [rbp+57h+hMem]; hMem
0x1800b9bed  call    cs:__imp_GlobalFree
0x1800b9bf3  mov     rcx, [rbp+57h+ppstm]
0x1800b9bf7  test    rcx, rcx
0x1800b9bfa  jz      short loc_1800B9C10
0x1800b9bfc  mov     rax, [rcx]
0x1800b9bff  mov     rax, [rax+10h]
0x1800b9c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9c08  mov     [rbp+57h+ppstm], 0
0x1800b9c10  mov     rcx, [rbp+57h+var_80]
0x1800b9c14  test    rcx, rcx
0x1800b9c17  jz      short loc_1800B9C2D
0x1800b9c19  mov     rax, [rcx]
0x1800b9c1c  mov     rax, [rax+10h]
0x1800b9c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9c25  mov     [rbp+57h+var_80], 0
0x1800b9c2d  test    r12, r12
0x1800b9c30  jz      short loc_1800B9C42
0x1800b9c32  mov     rax, [r12]
0x1800b9c36  mov     rcx, r12
  ... truncated ...
```
