# HrCreateJpegImgFromBitmap(IWICBitmapSource *,uchar * *,uint *)

- ea: `0x1800d92ac`
- end: `0x1800d97a9`
- name: `?HrCreateJpegImgFromBitmap@@YAJPEAUIWICBitmapSource@@PEAPEAEPEAI@Z`
- size: `1277`
- prototype: `__int64 __fastcall(struct IWICBitmapSource *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800d9180`

## callees

- `0x180043040`
- `0x180099c5c`
- `0x1800d92ac`
- `0x1800d97b0`
- `0x1800e2b48`
- `0x1800e2f90`
- `0x1800e3c04`
- `0x18017b528`
- `0x18017b540`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d9703`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d9703`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d9347`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d9347`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800d9385`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800d9385`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800d96df`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800d96df`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800d96d3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800d96d3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800d9711`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800d9711`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800d971f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800d971f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800d9317`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800d9317`

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
0x1800d92ac  mov     [rsp-8+arg_18], rbx
0x1800d92b1  push    rbp
0x1800d92b2  push    rsi
0x1800d92b3  push    rdi
0x1800d92b4  push    r12
0x1800d92b6  push    r13
0x1800d92b8  push    r14
0x1800d92ba  push    r15
0x1800d92bc  lea     rbp, [rsp-60h]
0x1800d92c1  sub     rsp, 160h
0x1800d92c8  mov     rax, cs:__security_cookie
0x1800d92cf  xor     rax, rsp
0x1800d92d2  mov     [rbp+90h+var_40], rax
0x1800d92d6  xor     r15d, r15d
0x1800d92d9  mov     r13, r8
0x1800d92dc  mov     r12, rdx
0x1800d92df  mov     rdi, rcx
0x1800d92e2  test    rcx, rcx
0x1800d92e5  jz      loc_1800D977D
0x1800d92eb  test    rdx, rdx
0x1800d92ee  jz      loc_1800D977D
0x1800d92f4  test    r8, r8
0x1800d92f7  jz      loc_1800D977D
0x1800d92fd  mov     [r8], r15d
0x1800d9300  mov     [rdx], r15
0x1800d9303  xor     edx, edx; dwBytes
0x1800d9305  mov     [rsp+190h+ppstm], r15
0x1800d930a  mov     [rsp+190h+var_158], r15
0x1800d930f  mov     [rsp+190h+var_160], r15
0x1800d9314  lea     ecx, [rdx+2]; uFlags
0x1800d9317  call    cs:__imp_GlobalAlloc
0x1800d931d  mov     [rsp+190h+var_148], r15
0x1800d9322  mov     esi, 8007000Eh
0x1800d9327  mov     r14, rax
0x1800d932a  test    rax, rax
0x1800d932d  jnz     short loc_1800D937B
0x1800d932f  mov     ebx, esi
0x1800d9331  mov     [rsp+190h+var_140], r15
0x1800d9336  mov     rdi, r15
0x1800d9339  mov     rsi, r15
0x1800d933c  test    ebx, ebx
0x1800d933e  js      loc_1800D9700
0x1800d9344  mov     rcx, r15; Size
0x1800d9347  call    cs:__imp_malloc
0x1800d934d  mov     rdi, rax
0x1800d9350  test    rax, rax
0x1800d9353  jz      short loc_1800D9371
0x1800d9355  mov     r8, r15; Size
0x1800d9358  mov     rdx, rsi; Src
0x1800d935b  mov     rcx, rax; void *
0x1800d935e  call    memcpy_0
0x1800d9363  mov     eax, 0FFFFFFFFh
0x1800d9368  cmp     r15, rax
0x1800d936b  jbe     loc_1800D96F6
0x1800d9371  mov     ebx, 8007000Eh
0x1800d9376  jmp     loc_1800D9700
0x1800d937b  lea     r8, [rsp+190h+ppstm]; ppstm
0x1800d9380  xor     edx, edx; fDeleteOnRelease
0x1800d9382  mov     rcx, r14; hGlobal
0x1800d9385  call    cs:__imp_CreateStreamOnHGlobal
0x1800d938b  mov     ebx, eax
0x1800d938d  test    eax, eax
0x1800d938f  js      loc_1800D953C
0x1800d9395  mov     ecx, 378h; Size
0x1800d939a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d939f  test    rax, rax
0x1800d93a2  jz      short loc_1800D932F
0x1800d93a4  mov     rcx, rax; this
0x1800d93a7  call    ??0CJpegTurboEncoder@@QEAA@XZ; CJpegTurboEncoder::CJpegTurboEncoder(void)
0x1800d93ac  mov     r9, rax
0x1800d93af  test    rax, rax
0x1800d93b2  jz      loc_1800D932F
0x1800d93b8  mov     rcx, [rax]
0x1800d93bb  lea     r8, [rsp+190h+var_158]
0x1800d93c0  lea     rdx, _GUID_00000103_a8f2_4877_ba0a_fd2b6645fb94
0x1800d93c7  mov     rax, [rcx]
0x1800d93ca  mov     rcx, r9
0x1800d93cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d93d2  mov     ebx, eax
0x1800d93d4  test    eax, eax
0x1800d93d6  js      loc_1800D953C
0x1800d93dc  mov     rcx, [rsp+190h+var_158]
0x1800d93e1  mov     r8d, 2
0x1800d93e7  mov     rdx, [rsp+190h+ppstm]
0x1800d93ec  mov     rax, [rcx]
0x1800d93ef  mov     rax, [rax+18h]
0x1800d93f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d93f8  mov     ebx, eax
0x1800d93fa  test    eax, eax
0x1800d93fc  js      loc_1800D953C
0x1800d9402  mov     rcx, [rsp+190h+var_158]
0x1800d9407  lea     r8, [rsp+190h+var_148]
0x1800d940c  lea     rdx, [rsp+190h+var_160]
0x1800d9411  mov     rax, [rcx]
0x1800d9414  mov     rax, [rax+50h]
0x1800d9418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d941d  mov     ebx, eax
0x1800d941f  test    eax, eax
0x1800d9421  js      loc_1800D953C
0x1800d9427  xor     edx, edx; Val
0x1800d9429  lea     rcx, [rbp+90h+var_C0]; void *
0x1800d942d  lea     r8d, [rdx+78h]; Size
0x1800d9431  call    memset_0
0x1800d9436  xor     edx, edx; Val
0x1800d9438  lea     rcx, [rbp+90h+var_110]; void *
0x1800d943c  lea     r8d, [rdx+48h]; Size
0x1800d9440  call    memset_0
0x1800d9445  mov     ecx, 9
0x1800d944a  call    ?GetEncoderOptionName@@YAPEAGW4EncoderOptions@@@Z; GetEncoderOptionName(EncoderOptions)
0x1800d944f  mov     ecx, 1
0x1800d9454  mov     [rbp+90h+var_B0], rax
0x1800d9458  call    ?GetEncoderOptionName@@YAPEAGW4EncoderOptions@@@Z; GetEncoderOptionName(EncoderOptions)
0x1800d945d  mov     ecx, 0Ah
0x1800d9462  mov     [rbp+90h+var_88], rax
0x1800d9466  call    ?GetEncoderOptionName@@YAPEAGW4EncoderOptions@@@Z; GetEncoderOptionName(EncoderOptions)
0x1800d946b  mov     rcx, [rsp+190h+var_148]
0x1800d9470  lea     r9, [rbp+90h+var_110]
0x1800d9474  mov     [rbp+90h+var_60], rax
0x1800d9478  lea     r8, [rbp+90h+var_C0]
0x1800d947c  mov     eax, 0Bh
0x1800d9481  mov     [rbp+90h+var_F0], 3F400000h
0x1800d9488  mov     [rbp+90h+var_110], ax
0x1800d948c  mov     edx, 3
0x1800d9491  or      eax, 0FFFFFFFFh
0x1800d9494  mov     [rbp+90h+var_D8], 2
0x1800d9498  mov     [rbp+90h+var_108], ax
0x1800d949c  mov     eax, 4
0x1800d94a1  mov     [rbp+90h+var_F8], ax
0x1800d94a5  mov     eax, 11h
0x1800d94aa  mov     [rbp+90h+var_E0], ax
0x1800d94ae  mov     rax, [rcx]
0x1800d94b1  mov     rax, [rax+20h]
0x1800d94b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d94ba  mov     ebx, eax
0x1800d94bc  test    eax, eax
0x1800d94be  js      short loc_1800D94D8
0x1800d94c0  mov     rcx, [rsp+190h+var_160]
0x1800d94c5  mov     rdx, [rsp+190h+var_148]
0x1800d94ca  mov     rax, [rcx]
0x1800d94cd  mov     rax, [rax+18h]
0x1800d94d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d94d6  mov     ebx, eax
0x1800d94d8  mov     rcx, [rsp+190h+var_148]
0x1800d94dd  test    rcx, rcx
0x1800d94e0  jz      short loc_1800D94F3
0x1800d94e2  mov     rax, [rcx]
0x1800d94e5  mov     rax, [rax+10h]
0x1800d94e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d94ee  mov     [rsp+190h+var_148], r15
0x1800d94f3  test    ebx, ebx
0x1800d94f5  js      short loc_1800D953C
0x1800d94f7  mov     rax, [rdi]
0x1800d94fa  lea     r8, [rsp+190h+var_150]
0x1800d94ff  lea     rdx, [rsp+190h+var_14C]
0x1800d9504  mov     [rsp+190h+var_14C], r15d
0x1800d9509  mov     rcx, rdi
0x1800d950c  mov     [rsp+190h+var_150], r15d
0x1800d9511  mov     rax, [rax+18h]
0x1800d9515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d951a  mov     ebx, eax
0x1800d951c  test    eax, eax
0x1800d951e  js      short loc_1800D953C
0x1800d9520  mov     rcx, [rsp+190h+var_160]
0x1800d9525  mov     r8d, [rsp+190h+var_150]
0x1800d952a  mov     edx, [rsp+190h+var_14C]
0x1800d952e  mov     rax, [rcx]
0x1800d9531  mov     rax, [rax+20h]
0x1800d9535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d953a  mov     ebx, eax
0x1800d953c  mov     [rsp+190h+var_140], r15
0x1800d9541  test    ebx, ebx
0x1800d9543  js      loc_1800D96C5
0x1800d9549  mov     rax, [rdi]
0x1800d954c  lea     rdx, [rsp+190h+Buf1]
0x1800d9551  xorps   xmm0, xmm0
0x1800d9554  mov     rcx, rdi
0x1800d9557  movups  [rsp+190h+Buf1], xmm0
0x1800d955c  mov     rax, [rax+20h]
0x1800d9560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9565  mov     ebx, eax
0x1800d9567  test    eax, eax
0x1800d9569  js      loc_1800D96AF
0x1800d956f  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat24bppBGR.Data1
0x1800d9576  mov     ebx, 10h
0x1800d957b  lea     rdx, GUID_WICPixelFormat8bppGray; Buf2
0x1800d9582  mov     r8d, ebx; Size
0x1800d9585  lea     rcx, [rsp+190h+Buf1]; Buf1
0x1800d958a  movdqu  xmmword ptr [rsp+190h+var_120.Data1], xmm0
0x1800d9590  call    memcmp_0
0x1800d9595  test    eax, eax
0x1800d9597  jz      loc_1800D9626
0x1800d959d  mov     r8d, ebx; Size
0x1800d95a0  lea     rdx, GUID_WICPixelFormat24bppBGR; Buf2
0x1800d95a7  lea     rcx, [rsp+190h+Buf1]; Buf1
0x1800d95ac  call    memcmp_0
0x1800d95b1  test    eax, eax
0x1800d95b3  jz      short loc_1800D9626
0x1800d95b5  mov     r8d, ebx; Size
0x1800d95b8  lea     rdx, GUID_WICPixelFormatBlackWhite; Buf2
0x1800d95bf  lea     rcx, [rsp+190h+Buf1]; Buf1
0x1800d95c4  call    memcmp_0
0x1800d95c9  test    eax, eax
0x1800d95cb  jz      short loc_1800D95FD
0x1800d95cd  mov     r8d, ebx; Size
0x1800d95d0  lea     rdx, GUID_WICPixelFormat2bppGray; Buf2
0x1800d95d7  lea     rcx, [rsp+190h+Buf1]; Buf1
0x1800d95dc  call    memcmp_0
0x1800d95e1  test    eax, eax
0x1800d95e3  jz      short loc_1800D95FD
0x1800d95e5  mov     r8d, ebx; Size
0x1800d95e8  lea     rdx, GUID_WICPixelFormat4bppGray; Buf2
0x1800d95ef  lea     rcx, [rsp+190h+Buf1]; Buf1
0x1800d95f4  call    memcmp_0
0x1800d95f9  test    eax, eax
0x1800d95fb  jnz     short loc_1800D960A
0x1800d95fd  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat8bppGray.Data1
0x1800d9604  movdqu  xmmword ptr [rsp+190h+var_120.Data1], xmm0
0x1800d960a  lea     r8, [rsp+190h+var_140]; struct IWICBitmapSource **
0x1800d960f  mov     rdx, rdi; struct IWICBitmapSource *
0x1800d9612  lea     rcx, [rsp+190h+var_120]; struct _GUID *
0x1800d9617  call    ?HrConvertBitmapNoHalftone@CFormatConverter@@SAJAEBU_GUID@@PEAUIWICBitmapSource@@PEAPEAU3@@Z; CFormatConverter::HrConvertBitmapNoHalftone(_GUID const &,IWICBitmapSource *,IWICBitmapSource * *)
0x1800d961c  test    eax, eax
0x1800d961e  cmovns  rdi, [rsp+190h+var_140]
0x1800d9624  jmp     short loc_1800D9631
0x1800d9626  movaps  xmm0, [rsp+190h+Buf1]
0x1800d962b  movdqa  xmmword ptr [rsp+190h+var_120.Data1], xmm0
0x1800d9631  mov     rcx, [rsp+190h+var_160]
0x1800d9636  lea     rdx, [rsp+190h+var_120]
0x1800d963b  mov     rax, [rcx]
0x1800d963e  mov     rax, [rax+30h]
0x1800d9642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9647  mov     ebx, eax
0x1800d9649  test    eax, eax
0x1800d964b  js      short loc_1800D96AF
0x1800d964d  mov     rcx, [rsp+190h+var_160]
0x1800d9652  xor     r8d, r8d
0x1800d9655  mov     rdx, rdi
0x1800d9658  mov     rax, [rcx]
0x1800d965b  mov     rax, [rax+58h]
0x1800d965f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9664  mov     ebx, eax
0x1800d9666  test    eax, eax
0x1800d9668  js      short loc_1800D96AF
0x1800d966a  mov     rcx, [rsp+190h+var_160]
0x1800d966f  mov     rax, [rcx]
0x1800d9672  mov     rax, [rax+60h]
0x1800d9676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d967b  mov     ebx, eax
0x1800d967d  test    eax, eax
0x1800d967f  js      short loc_1800D9694
0x1800d9681  mov     rcx, [rsp+190h+var_158]
0x1800d9686  mov     rax, [rcx]
0x1800d9689  mov     rax, [rax+58h]
0x1800d968d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9692  mov     ebx, eax
0x1800d9694  mov     rcx, [rsp+190h+ppstm]
0x1800d9699  test    rcx, rcx
0x1800d969c  jz      short loc_1800D96AF
0x1800d969e  mov     rax, [rcx]
0x1800d96a1  mov     rax, [rax+10h]
0x1800d96a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d96aa  mov     [rsp+190h+ppstm], r15
0x1800d96af  mov     rcx, [rsp+190h+var_140]
0x1800d96b4  test    rcx, rcx
0x1800d96b7  jz      short loc_1800D96C5
0x1800d96b9  mov     rax, [rcx]
0x1800d96bc  mov     rax, [rax+10h]
0x1800d96c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d96c5  mov     rdi, r15
0x1800d96c8  test    ebx, ebx
0x1800d96ca  js      loc_1800D9339
0x1800d96d0  mov     rcx, r14; hMem
0x1800d96d3  call    cs:__imp_GlobalSize
0x1800d96d9  mov     rcx, r14; hMem
0x1800d96dc  mov     r15, rax
0x1800d96df  call    cs:__imp_GlobalLock
0x1800d96e5  mov     rsi, rax
0x1800d96e8  test    rax, rax
0x1800d96eb  jnz     loc_1800D9344
0x1800d96f1  jmp     loc_1800D9371
0x1800d96f6  mov     [r12], rdi
0x1800d96fa  xor     edi, edi
0x1800d96fc  mov     [r13+0], r15d
0x1800d9700  mov     rcx, rdi; Block
0x1800d9703  call    cs:__imp_free
0x1800d9709  test    rsi, rsi
0x1800d970c  jz      short loc_1800D9717
0x1800d970e  mov     rcx, r14; hMem
0x1800d9711  call    cs:__imp_GlobalUnlock
0x1800d9717  test    r14, r14
0x1800d971a  jz      short loc_1800D9725
0x1800d971c  mov     rcx, r14; hMem
0x1800d971f  call    cs:__imp_GlobalFree
0x1800d9725  mov     rcx, [rsp+190h+var_160]
0x1800d972a  test    rcx, rcx
0x1800d972d  jz      short loc_1800D9744
0x1800d972f  mov     rax, [rcx]
0x1800d9732  mov     rax, [rax+10h]
0x1800d9736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d973b  mov     [rsp+190h+var_160], 0
  ... truncated ...
```
