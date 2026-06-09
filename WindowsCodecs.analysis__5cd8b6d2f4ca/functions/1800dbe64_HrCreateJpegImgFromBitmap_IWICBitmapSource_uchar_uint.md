# HrCreateJpegImgFromBitmap(IWICBitmapSource *,uchar * *,uint *)

- ea: `0x1800dbe64`
- end: `0x1800dc396`
- name: `?HrCreateJpegImgFromBitmap@@YAJPEAUIWICBitmapSource@@PEAPEAEPEAI@Z`
- size: `1330`
- prototype: `__int64 __fastcall(struct IWICBitmapSource *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800dbd30`

## callees

- `0x180036900`
- `0x18005b8ac`
- `0x1800dbe64`
- `0x1800dc39c`
- `0x1800e5a18`
- `0x1800e5e60`
- `0x1800e6af4`
- `0x18017e438`
- `0x18017e450`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dc2dd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dc2dd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800dbf05`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800dbf05`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800dbf49`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800dbf49`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800dc2b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800dc2b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800dc2a1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800dc2a1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800dc2f1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800dc2f1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc305`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc305`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800dbecf`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800dbecf`

## pseudocode

```c
__int64 __fastcall HrCreateJpegImgFromBitmap(struct IWICBitmapSource *a1, unsigned __int8 **a2, unsigned int *a3)
{
  struct IWICBitmapSource *v5; // rdi
  HGLOBAL v6; // rax
  void *v7; // r14
  HRESULT v8; // ebx
  unsigned __int8 *v9; // rdi
  const void *v10; // rsi
  unsigned __int8 *v11; // rax
  CJpegTurboEncoder *v12; // rax
  CJpegTurboEncoder *v13; // rax
  struct IWICBitmapSource v14; // rax
  struct IWICBitmapSourceVtbl *lpVtbl; // rax
  SIZE_T v16; // r15
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  struct IWICBitmapSource *v23; // [rsp+50h] [rbp-B0h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID Buf1; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v26; // [rsp+70h] [rbp-90h] BYREF
  _WORD v27[16]; // [rsp+80h] [rbp-80h] BYREF
  int v28; // [rsp+A0h] [rbp-60h]
  __int16 v29; // [rsp+B0h] [rbp-50h]
  char v30; // [rsp+B8h] [rbp-48h]
  _BYTE v31[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 EncoderOptionName; // [rsp+E0h] [rbp-20h]
  __int64 v33; // [rsp+108h] [rbp+8h]
  __int64 v34; // [rsp+130h] [rbp+30h]

  v5 = a1;
  if ( !a1 || !a2 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  *a2 = 0;
  ppstm = 0;
  v19 = 0;
  v18 = 0;
  v6 = GlobalAlloc(2u, 0);
  v22 = 0;
  v7 = v6;
  if ( !v6 )
    goto LABEL_5;
  v8 = CreateStreamOnHGlobal(v6, 0, &ppstm);
  if ( v8 >= 0 )
  {
    v12 = (CJpegTurboEncoder *)operator new(0x378u);
    if ( !v12 || (v13 = CJpegTurboEncoder::CJpegTurboEncoder(v12)) == 0 )
    {
LABEL_5:
      v8 = -2147024882;
      v23 = 0;
      v9 = 0;
      goto LABEL_6;
    }
    v8 = (**(__int64 (__fastcall ***)(CJpegTurboEncoder *, GUID *, __int64 *))v13)(
           v13,
           &GUID_00000103_a8f2_4877_ba0a_fd2b6645fb94,
           &v19);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, LPSTREAM, __int64))(*(_QWORD *)v19 + 24LL))(v19, ppstm, 2);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v19 + 80LL))(v19, &v18, &v22);
        if ( v8 >= 0 )
        {
          memset_0(v31, 0, 0x78u);
          memset_0(v27, 0, 0x48u);
          EncoderOptionName = GetEncoderOptionName(9);
          v33 = GetEncoderOptionName(1);
          v34 = GetEncoderOptionName(10);
          v28 = 1061158912;
          v27[0] = 11;
          v30 = 2;
          v27[4] = -1;
          v27[12] = 4;
          v29 = 17;
          v8 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, _WORD *))(*(_QWORD *)v22 + 32LL))(v22, 3, v31, v27);
          if ( v8 >= 0 )
            v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 24LL))(v18, v22);
          if ( v22 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            v22 = 0;
          }
          if ( v8 >= 0 )
          {
            v14.lpVtbl = v5->lpVtbl;
            v21 = 0;
            v20 = 0;
            v8 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))v14.lpVtbl->GetSize)(
                   v5,
                   &v21,
                   &v20);
            if ( v8 >= 0 )
              v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v18 + 32LL))(v18, v21, v20);
          }
        }
      }
    }
  }
  v23 = 0;
  if ( v8 >= 0 )
  {
    lpVtbl = v5->lpVtbl;
    Buf1 = 0;
    v8 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, struct _GUID *))lpVtbl->GetPixelFormat)(v5, &Buf1);
    if ( v8 >= 0 )
    {
      v26 = GUID_WICPixelFormat24bppBGR;
      if ( !memcmp_0(&Buf1, &GUID_WICPixelFormat8bppGray, 0x10u)
        || !memcmp_0(&Buf1, &GUID_WICPixelFormat24bppBGR, 0x10u) )
      {
        v26 = Buf1;
      }
      else
      {
        if ( !memcmp_0(&Buf1, &GUID_WICPixelFormatBlackWhite, 0x10u)
          || !memcmp_0(&Buf1, &GUID_WICPixelFormat2bppGray, 0x10u)
          || !memcmp_0(&Buf1, &GUID_WICPixelFormat4bppGray, 0x10u) )
        {
          v26 = GUID_WICPixelFormat8bppGray;
        }
        if ( CFormatConverter::HrConvertBitmapNoHalftone(&v26, v5, &v23) >= 0 )
          v5 = v23;
      }
      v8 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v18 + 48LL))(v18, &v26);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, struct IWICBitmapSource *, _QWORD))(*(_QWORD *)v18 + 88LL))(v18, v5, 0);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 96LL))(v18);
          if ( v8 >= 0 )
            v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 88LL))(v19);
          if ( ppstm )
          {
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
            ppstm = 0;
          }
        }
      }
    }
    if ( v23 )
      ((void (__fastcall *)(struct IWICBitmapSource *))v23->lpVtbl->Release)(v23);
  }
  v9 = 0;
  if ( v8 >= 0 )
  {
    v16 = GlobalSize(v7);
    v10 = GlobalLock(v7);
    if ( v10 && (v11 = (unsigned __int8 *)malloc(v16), (v9 = v11) != 0) && (memcpy_0(v11, v10, v16), v16 <= 0xFFFFFFFF) )
    {
      *a2 = v9;
      v9 = 0;
      *a3 = v16;
    }
    else
    {
      v8 = -2147024882;
    }
    goto LABEL_47;
  }
LABEL_6:
  v10 = 0;
LABEL_47:
  free(v9);
  if ( v10 )
    GlobalUnlock(v7);
  if ( v7 )
    GlobalFree(v7);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( ppstm )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800dbe64  mov     [rsp-8+arg_18], rbx
0x1800dbe69  push    rbp
0x1800dbe6a  push    rsi
0x1800dbe6b  push    rdi
0x1800dbe6c  push    r12
0x1800dbe6e  push    r13
0x1800dbe70  push    r14
0x1800dbe72  push    r15
0x1800dbe74  lea     rbp, [rsp-60h]
0x1800dbe79  sub     rsp, 160h
0x1800dbe80  mov     rax, cs:__security_cookie
0x1800dbe87  xor     rax, rsp
0x1800dbe8a  mov     [rbp+90h+var_40], rax
0x1800dbe8e  xor     r15d, r15d
0x1800dbe91  mov     r13, r8
0x1800dbe94  mov     r12, rdx
0x1800dbe97  mov     rdi, rcx
0x1800dbe9a  test    rcx, rcx
0x1800dbe9d  jz      loc_1800DC369
0x1800dbea3  test    rdx, rdx
0x1800dbea6  jz      loc_1800DC369
0x1800dbeac  test    r8, r8
0x1800dbeaf  jz      loc_1800DC369
0x1800dbeb5  mov     [r8], r15d
0x1800dbeb8  mov     [rdx], r15
0x1800dbebb  xor     edx, edx; dwBytes
0x1800dbebd  mov     [rsp+190h+ppstm], r15
0x1800dbec2  mov     [rsp+190h+var_158], r15
0x1800dbec7  mov     [rsp+190h+var_160], r15
0x1800dbecc  lea     ecx, [rdx+2]; uFlags
0x1800dbecf  call    cs:__imp_GlobalAlloc
0x1800dbed6  nop     dword ptr [rax+rax+00h]
0x1800dbedb  mov     [rsp+190h+var_148], r15
0x1800dbee0  mov     esi, 8007000Eh
0x1800dbee5  mov     r14, rax
0x1800dbee8  test    rax, rax
0x1800dbeeb  jnz     short loc_1800DBF3F
0x1800dbeed  mov     ebx, esi
0x1800dbeef  mov     [rsp+190h+var_140], r15
0x1800dbef4  mov     rdi, r15
0x1800dbef7  mov     rsi, r15
0x1800dbefa  test    ebx, ebx
0x1800dbefc  js      loc_1800DC2DA
0x1800dbf02  mov     rcx, r15; Size
0x1800dbf05  call    cs:__imp_malloc
0x1800dbf0c  nop     dword ptr [rax+rax+00h]
0x1800dbf11  mov     rdi, rax
0x1800dbf14  test    rax, rax
0x1800dbf17  jz      short loc_1800DBF35
0x1800dbf19  mov     r8, r15; Size
0x1800dbf1c  mov     rdx, rsi; Src
0x1800dbf1f  mov     rcx, rax; void *
0x1800dbf22  call    memcpy_0
0x1800dbf27  mov     eax, 0FFFFFFFFh
0x1800dbf2c  cmp     r15, rax
0x1800dbf2f  jbe     loc_1800DC2D0
0x1800dbf35  mov     ebx, 8007000Eh
0x1800dbf3a  jmp     loc_1800DC2DA
0x1800dbf3f  lea     r8, [rsp+190h+ppstm]; ppstm
0x1800dbf44  xor     edx, edx; fDeleteOnRelease
0x1800dbf46  mov     rcx, r14; hGlobal
0x1800dbf49  call    cs:__imp_CreateStreamOnHGlobal
0x1800dbf50  nop     dword ptr [rax+rax+00h]
0x1800dbf55  mov     ebx, eax
0x1800dbf57  test    eax, eax
0x1800dbf59  js      loc_1800DC10A
0x1800dbf5f  mov     ecx, 378h; Size
0x1800dbf64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dbf69  test    rax, rax
0x1800dbf6c  jz      loc_1800DBEED
0x1800dbf72  mov     rcx, rax; this
0x1800dbf75  call    ??0CJpegTurboEncoder@@QEAA@XZ; CJpegTurboEncoder::CJpegTurboEncoder(void)
0x1800dbf7a  mov     r9, rax
0x1800dbf7d  test    rax, rax
0x1800dbf80  jz      loc_1800DBEED
0x1800dbf86  mov     rcx, [rax]
0x1800dbf89  lea     r8, [rsp+190h+var_158]
0x1800dbf8e  lea     rdx, _GUID_00000103_a8f2_4877_ba0a_fd2b6645fb94
0x1800dbf95  mov     rax, [rcx]
0x1800dbf98  mov     rcx, r9
0x1800dbf9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbfa0  mov     ebx, eax
0x1800dbfa2  test    eax, eax
0x1800dbfa4  js      loc_1800DC10A
0x1800dbfaa  mov     rcx, [rsp+190h+var_158]
0x1800dbfaf  mov     r8d, 2
0x1800dbfb5  mov     rdx, [rsp+190h+ppstm]
0x1800dbfba  mov     rax, [rcx]
0x1800dbfbd  mov     rax, [rax+18h]
0x1800dbfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbfc6  mov     ebx, eax
0x1800dbfc8  test    eax, eax
0x1800dbfca  js      loc_1800DC10A
0x1800dbfd0  mov     rcx, [rsp+190h+var_158]
0x1800dbfd5  lea     r8, [rsp+190h+var_148]
0x1800dbfda  lea     rdx, [rsp+190h+var_160]
0x1800dbfdf  mov     rax, [rcx]
0x1800dbfe2  mov     rax, [rax+50h]
0x1800dbfe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbfeb  mov     ebx, eax
0x1800dbfed  test    eax, eax
0x1800dbfef  js      loc_1800DC10A
0x1800dbff5  xor     edx, edx; Val
0x1800dbff7  lea     rcx, [rbp+90h+var_C0]; void *
0x1800dbffb  lea     r8d, [rdx+78h]; Size
0x1800dbfff  call    memset_0
0x1800dc004  xor     edx, edx; Val
0x1800dc006  lea     rcx, [rbp+90h+var_110]; void *
0x1800dc00a  lea     r8d, [rdx+48h]; Size
0x1800dc00e  call    memset_0
0x1800dc013  mov     ecx, 9
0x1800dc018  call    ?GetEncoderOptionName@@YAPEAGW4EncoderOptions@@@Z; GetEncoderOptionName(EncoderOptions)
0x1800dc01d  mov     ecx, 1
0x1800dc022  mov     [rbp+90h+var_B0], rax
0x1800dc026  call    ?GetEncoderOptionName@@YAPEAGW4EncoderOptions@@@Z; GetEncoderOptionName(EncoderOptions)
0x1800dc02b  mov     ecx, 0Ah
0x1800dc030  mov     [rbp+90h+var_88], rax
0x1800dc034  call    ?GetEncoderOptionName@@YAPEAGW4EncoderOptions@@@Z; GetEncoderOptionName(EncoderOptions)
0x1800dc039  mov     rcx, [rsp+190h+var_148]
0x1800dc03e  lea     r9, [rbp+90h+var_110]
0x1800dc042  mov     [rbp+90h+var_60], rax
0x1800dc046  lea     r8, [rbp+90h+var_C0]
0x1800dc04a  mov     eax, 0Bh
0x1800dc04f  mov     [rbp+90h+var_F0], 3F400000h
0x1800dc056  mov     [rbp+90h+var_110], ax
0x1800dc05a  mov     edx, 3
0x1800dc05f  or      eax, 0FFFFFFFFh
0x1800dc062  mov     [rbp+90h+var_D8], 2
0x1800dc066  mov     [rbp+90h+var_108], ax
0x1800dc06a  mov     eax, 4
0x1800dc06f  mov     [rbp+90h+var_F8], ax
0x1800dc073  mov     eax, 11h
0x1800dc078  mov     [rbp+90h+var_E0], ax
0x1800dc07c  mov     rax, [rcx]
0x1800dc07f  mov     rax, [rax+20h]
0x1800dc083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc088  mov     ebx, eax
0x1800dc08a  test    eax, eax
0x1800dc08c  js      short loc_1800DC0A6
0x1800dc08e  mov     rcx, [rsp+190h+var_160]
0x1800dc093  mov     rdx, [rsp+190h+var_148]
0x1800dc098  mov     rax, [rcx]
0x1800dc09b  mov     rax, [rax+18h]
0x1800dc09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc0a4  mov     ebx, eax
0x1800dc0a6  mov     rcx, [rsp+190h+var_148]
0x1800dc0ab  test    rcx, rcx
0x1800dc0ae  jz      short loc_1800DC0C1
0x1800dc0b0  mov     rax, [rcx]
0x1800dc0b3  mov     rax, [rax+10h]
0x1800dc0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc0bc  mov     [rsp+190h+var_148], r15
0x1800dc0c1  test    ebx, ebx
0x1800dc0c3  js      short loc_1800DC10A
0x1800dc0c5  mov     rax, [rdi]
0x1800dc0c8  lea     r8, [rsp+190h+var_150]
0x1800dc0cd  lea     rdx, [rsp+190h+var_14C]
0x1800dc0d2  mov     [rsp+190h+var_14C], r15d
0x1800dc0d7  mov     rcx, rdi
0x1800dc0da  mov     [rsp+190h+var_150], r15d
0x1800dc0df  mov     rax, [rax+18h]
0x1800dc0e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc0e8  mov     ebx, eax
0x1800dc0ea  test    eax, eax
0x1800dc0ec  js      short loc_1800DC10A
0x1800dc0ee  mov     rcx, [rsp+190h+var_160]
0x1800dc0f3  mov     r8d, [rsp+190h+var_150]
0x1800dc0f8  mov     edx, [rsp+190h+var_14C]
0x1800dc0fc  mov     rax, [rcx]
0x1800dc0ff  mov     rax, [rax+20h]
0x1800dc103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc108  mov     ebx, eax
0x1800dc10a  mov     [rsp+190h+var_140], r15
0x1800dc10f  test    ebx, ebx
0x1800dc111  js      loc_1800DC293
0x1800dc117  mov     rax, [rdi]
0x1800dc11a  lea     rdx, [rsp+190h+Buf1]
0x1800dc11f  xorps   xmm0, xmm0
0x1800dc122  mov     rcx, rdi
0x1800dc125  movups  [rsp+190h+Buf1], xmm0
0x1800dc12a  mov     rax, [rax+20h]
0x1800dc12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc133  mov     ebx, eax
0x1800dc135  test    eax, eax
0x1800dc137  js      loc_1800DC27D
0x1800dc13d  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat24bppBGR.Data1
0x1800dc144  mov     ebx, 10h
0x1800dc149  lea     rdx, GUID_WICPixelFormat8bppGray; Buf2
0x1800dc150  mov     r8d, ebx; Size
0x1800dc153  lea     rcx, [rsp+190h+Buf1]; Buf1
0x1800dc158  movdqu  xmmword ptr [rsp+190h+var_120.Data1], xmm0
0x1800dc15e  call    memcmp_0
0x1800dc163  test    eax, eax
0x1800dc165  jz      loc_1800DC1F4
0x1800dc16b  mov     r8d, ebx; Size
0x1800dc16e  lea     rdx, GUID_WICPixelFormat24bppBGR; Buf2
0x1800dc175  lea     rcx, [rsp+190h+Buf1]; Buf1
0x1800dc17a  call    memcmp_0
0x1800dc17f  test    eax, eax
0x1800dc181  jz      short loc_1800DC1F4
0x1800dc183  mov     r8d, ebx; Size
0x1800dc186  lea     rdx, GUID_WICPixelFormatBlackWhite; Buf2
0x1800dc18d  lea     rcx, [rsp+190h+Buf1]; Buf1
0x1800dc192  call    memcmp_0
0x1800dc197  test    eax, eax
0x1800dc199  jz      short loc_1800DC1CB
0x1800dc19b  mov     r8d, ebx; Size
0x1800dc19e  lea     rdx, GUID_WICPixelFormat2bppGray; Buf2
0x1800dc1a5  lea     rcx, [rsp+190h+Buf1]; Buf1
0x1800dc1aa  call    memcmp_0
0x1800dc1af  test    eax, eax
0x1800dc1b1  jz      short loc_1800DC1CB
0x1800dc1b3  mov     r8d, ebx; Size
0x1800dc1b6  lea     rdx, GUID_WICPixelFormat4bppGray; Buf2
0x1800dc1bd  lea     rcx, [rsp+190h+Buf1]; Buf1
0x1800dc1c2  call    memcmp_0
0x1800dc1c7  test    eax, eax
0x1800dc1c9  jnz     short loc_1800DC1D8
0x1800dc1cb  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat8bppGray.Data1
0x1800dc1d2  movdqu  xmmword ptr [rsp+190h+var_120.Data1], xmm0
0x1800dc1d8  lea     r8, [rsp+190h+var_140]; struct IWICBitmapSource **
0x1800dc1dd  mov     rdx, rdi; struct IWICBitmapSource *
0x1800dc1e0  lea     rcx, [rsp+190h+var_120]; struct _GUID *
0x1800dc1e5  call    ?HrConvertBitmapNoHalftone@CFormatConverter@@SAJAEBU_GUID@@PEAUIWICBitmapSource@@PEAPEAU3@@Z; CFormatConverter::HrConvertBitmapNoHalftone(_GUID const &,IWICBitmapSource *,IWICBitmapSource * *)
0x1800dc1ea  test    eax, eax
0x1800dc1ec  cmovns  rdi, [rsp+190h+var_140]
0x1800dc1f2  jmp     short loc_1800DC1FF
0x1800dc1f4  movaps  xmm0, [rsp+190h+Buf1]
0x1800dc1f9  movdqa  xmmword ptr [rsp+190h+var_120.Data1], xmm0
0x1800dc1ff  mov     rcx, [rsp+190h+var_160]
0x1800dc204  lea     rdx, [rsp+190h+var_120]
0x1800dc209  mov     rax, [rcx]
0x1800dc20c  mov     rax, [rax+30h]
0x1800dc210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc215  mov     ebx, eax
0x1800dc217  test    eax, eax
0x1800dc219  js      short loc_1800DC27D
0x1800dc21b  mov     rcx, [rsp+190h+var_160]
0x1800dc220  xor     r8d, r8d
0x1800dc223  mov     rdx, rdi
0x1800dc226  mov     rax, [rcx]
0x1800dc229  mov     rax, [rax+58h]
0x1800dc22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc232  mov     ebx, eax
0x1800dc234  test    eax, eax
0x1800dc236  js      short loc_1800DC27D
0x1800dc238  mov     rcx, [rsp+190h+var_160]
0x1800dc23d  mov     rax, [rcx]
0x1800dc240  mov     rax, [rax+60h]
0x1800dc244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc249  mov     ebx, eax
0x1800dc24b  test    eax, eax
0x1800dc24d  js      short loc_1800DC262
0x1800dc24f  mov     rcx, [rsp+190h+var_158]
0x1800dc254  mov     rax, [rcx]
0x1800dc257  mov     rax, [rax+58h]
0x1800dc25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc260  mov     ebx, eax
0x1800dc262  mov     rcx, [rsp+190h+ppstm]
0x1800dc267  test    rcx, rcx
0x1800dc26a  jz      short loc_1800DC27D
0x1800dc26c  mov     rax, [rcx]
0x1800dc26f  mov     rax, [rax+10h]
0x1800dc273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc278  mov     [rsp+190h+ppstm], r15
0x1800dc27d  mov     rcx, [rsp+190h+var_140]
0x1800dc282  test    rcx, rcx
0x1800dc285  jz      short loc_1800DC293
0x1800dc287  mov     rax, [rcx]
0x1800dc28a  mov     rax, [rax+10h]
0x1800dc28e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc293  mov     rdi, r15
0x1800dc296  test    ebx, ebx
0x1800dc298  js      loc_1800DBEF7
0x1800dc29e  mov     rcx, r14; hMem
0x1800dc2a1  call    cs:__imp_GlobalSize
0x1800dc2a8  nop     dword ptr [rax+rax+00h]
0x1800dc2ad  mov     rcx, r14; hMem
0x1800dc2b0  mov     r15, rax
0x1800dc2b3  call    cs:__imp_GlobalLock
0x1800dc2ba  nop     dword ptr [rax+rax+00h]
0x1800dc2bf  mov     rsi, rax
0x1800dc2c2  test    rax, rax
0x1800dc2c5  jnz     loc_1800DBF02
0x1800dc2cb  jmp     loc_1800DBF35
0x1800dc2d0  mov     [r12], rdi
0x1800dc2d4  xor     edi, edi
0x1800dc2d6  mov     [r13+0], r15d
0x1800dc2da  mov     rcx, rdi; Block
0x1800dc2dd  call    cs:__imp_free
0x1800dc2e4  nop     dword ptr [rax+rax+00h]
0x1800dc2e9  test    rsi, rsi
0x1800dc2ec  jz      short loc_1800DC2FD
0x1800dc2ee  mov     rcx, r14; hMem
0x1800dc2f1  call    cs:__imp_GlobalUnlock
0x1800dc2f8  nop     dword ptr [rax+rax+00h]
0x1800dc2fd  test    r14, r14
0x1800dc300  jz      short loc_1800DC311
0x1800dc302  mov     rcx, r14; hMem
0x1800dc305  call    cs:__imp_GlobalFree
  ... truncated ...
```
