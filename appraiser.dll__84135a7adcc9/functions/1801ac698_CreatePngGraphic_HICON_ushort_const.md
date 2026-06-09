# CreatePngGraphic(HICON__ *,ushort const *)

- ea: `0x1801ac698`
- end: `0x1801acb17`
- name: `?CreatePngGraphic@@YAJPEAUHICON__@@PEBG@Z`
- size: `1151`
- prototype: `__int64 __fastcall(HICON, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801acbdc`
- `0x1801ad01c`
- `0x1801ad8a8`

## callees

- `0x180008570`
- `0x1801ac698`
- `0x1801acb20`
- `0x1801acef4`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1801ac719`
- `KERNEL32!GetProcAddress` at `0x1801ac895`
- `KERNEL32!GetProcAddress` at `0x1801ac8ed`
- `KERNEL32!GetProcAddress` at `0x1801ac9a9`
- `KERNEL32!GetProcAddress` at `0x1801aca59`
- `KERNEL32!GetProcAddress` at `0x1801acadb`
- `KERNEL32!GetProcAddress` at `0x1801ac719`
- `KERNEL32!GetProcAddress` at `0x1801ac895`
- `KERNEL32!GetProcAddress` at `0x1801ac8ed`
- `KERNEL32!GetProcAddress` at `0x1801ac9a9`
- `KERNEL32!GetProcAddress` at `0x1801aca59`
- `KERNEL32!GetProcAddress` at `0x1801acadb`
- `USER32!GetIconInfo` at `0x1801ac73c`
- `USER32!GetIconInfo` at `0x1801ac73c`
- `GDI32!GetObjectW` at `0x1801ac769`
- `GDI32!GetObjectW` at `0x1801ac769`
- `GDI32!DeleteObject` at `0x1801acaa4`
- `GDI32!DeleteObject` at `0x1801acaa4`
- `GDI32!GetDIBits` at `0x1801ac829`
- `GDI32!GetDIBits` at `0x1801ac829`
- `GDI32!CreateCompatibleDC` at `0x1801ac790`
- `GDI32!CreateCompatibleDC` at `0x1801ac790`
- `GDI32!DeleteDC` at `0x1801acab2`
- `GDI32!DeleteDC` at `0x1801acab2`
- `GDI32!CreateDIBSection` at `0x1801ac7f0`
- `GDI32!CreateDIBSection` at `0x1801ac7f0`

## string_xrefs

- `0x1801ac8e6`: `GdipCreateBitmapFromScan0`

## pseudocode

```c
__int64 __fastcall CreatePngGraphic(HICON a1, const unsigned __int16 *a2)
{
  unsigned int v3; // edi
  FARPROC ProcAddress; // rax
  int v5; // r15d
  HDC CompatibleDC; // rax
  HDC v7; // rdi
  HBITMAP v8; // r12
  int v9; // edx
  int v10; // ecx
  FARPROC v11; // rax
  struct Gdiplus::Bitmap *PngGraphicFromMonochrome; // rbx
  HMODULE v13; // rcx
  unsigned int v14; // r14d
  int v15; // esi
  unsigned int v16; // r13d
  FARPROC v17; // rax
  int v18; // r14d
  const unsigned __int16 *v19; // rcx
  int i; // esi
  __int64 v21; // rdx
  int v22; // r13d
  unsigned __int8 v23; // r8
  FARPROC v24; // rax
  __int64 v25; // rsi
  FARPROC v26; // rax
  __int64 v27; // rbx
  FARPROC v28; // rax
  unsigned __int8 v30; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v31; // [rsp+41h] [rbp-BFh]
  unsigned __int8 v32; // [rsp+42h] [rbp-BEh]
  unsigned __int8 v33; // [rsp+43h] [rbp-BDh]
  int v34; // [rsp+44h] [rbp-BCh]
  void *ppvBits; // [rsp+48h] [rbp-B8h] BYREF
  __int128 pv; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v37; // [rsp+60h] [rbp-A0h]
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v41; // [rsp+88h] [rbp-78h]
  int v42; // [rsp+90h] [rbp-70h] BYREF
  __int64 v43; // [rsp+98h] [rbp-68h]
  __int64 v44; // [rsp+A0h] [rbp-60h]
  ICONINFO piconinfo; // [rsp+A8h] [rbp-58h] BYREF
  BITMAPINFO pbmi; // [rsp+C8h] [rbp-38h] BYREF
  struct _GUID v47; // [rsp+F8h] [rbp-8h] BYREF

  v41 = a2;
  v43 = 0;
  v44 = 0;
  v39 = 0;
  v3 = -2147467259;
  v34 = -2147467259;
  v42 = 1;
  v47 = 0;
  pv = 0;
  v37 = 0;
  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( gdiplusModule )
  {
    ProcAddress = GetProcAddress(gdiplusModule, "GdiplusStartup");
    if ( ProcAddress )
      ((void (__fastcall *)(__int64 *, int *, _QWORD))ProcAddress)(&v39, &v42, 0);
  }
  if ( GetIconInfo(a1, &piconinfo) )
  {
    v5 = 6;
    if ( piconinfo.hbmColor && GetObjectW(piconinfo.hbmColor, 32, &pv) && (_DWORD)v37 == 2097153 )
    {
      CompatibleDC = CreateCompatibleDC(0);
      v7 = CompatibleDC;
      if ( !CompatibleDC )
      {
        v3 = -2147467259;
        goto LABEL_50;
      }
      pbmi.bmiHeader.biSize = 40;
      pbmi.bmiHeader.biWidth = DWORD1(pv);
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      pbmi.bmiHeader.biHeight = -DWORD2(pv);
      memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
      ppvBits = 0;
      v8 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
      if ( !v8 )
        goto LABEL_47;
      if ( !GetDIBits(v7, piconinfo.hbmColor, 0, DWORD2(pv), ppvBits, &pbmi, 0) )
        goto LABEL_45;
      v9 = 0;
      if ( SDWORD1(pv) > 0 )
      {
        while ( 1 )
        {
          v10 = 0;
          if ( SDWORD2(pv) > 0 )
            break;
LABEL_15:
          if ( ++v9 >= SDWORD1(pv) )
            goto LABEL_35;
        }
        while ( !*((_BYTE *)ppvBits + 4 * v9 + 4 * DWORD2(pv) * v10 + 3) )
        {
          if ( ++v10 >= SDWORD2(pv) )
            goto LABEL_15;
        }
        if ( gdiplusModule )
        {
          v11 = GetProcAddress(gdiplusModule, "GdipAlloc");
          if ( v11 )
          {
            PngGraphicFromMonochrome = (struct Gdiplus::Bitmap *)((__int64 (__fastcall *)(__int64))v11)(24);
            if ( PngGraphicFromMonochrome )
            {
              v13 = gdiplusModule;
              v14 = DWORD2(pv);
              v15 = 6;
              v16 = DWORD1(pv);
              *(_QWORD *)PngGraphicFromMonochrome = &Gdiplus::Image::`vftable';
              v38 = 0;
              if ( v13 )
              {
                v17 = GetProcAddress(v13, "GdipCreateBitmapFromScan0");
                if ( v17 )
                  v15 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64, _QWORD, __int64 *))v17)(
                          v16,
                          v14,
                          0,
                          2498570,
                          0,
                          &v38);
              }
              *((_QWORD *)PngGraphicFromMonochrome + 1) = v38;
              v18 = 0;
              *((_DWORD *)PngGraphicFromMonochrome + 4) = v15;
              v19 = (const unsigned __int16 *)DWORD1(pv);
              if ( SDWORD1(pv) <= 0 )
              {
LABEL_37:
                if ( (unsigned int)GetEncoderClsid(v19, &v47) )
                {
                  if ( gdiplusModule
                    && (v25 = *((_QWORD *)PngGraphicFromMonochrome + 1),
                        (v26 = GetProcAddress(gdiplusModule, "GdipSaveImageToFile")) != 0)
                    && (v5 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, struct _GUID *, _QWORD))v26)(
                               v25,
                               v41,
                               &v47,
                               0)) == 0 )
                  {
                    v34 = 0;
                  }
                  else
                  {
                    *((_DWORD *)PngGraphicFromMonochrome + 4) = v5;
                  }
                }
                (**(void (__fastcall ***)(struct Gdiplus::Bitmap *, __int64))PngGraphicFromMonochrome)(
                  PngGraphicFromMonochrome,
                  1);
LABEL_44:
                if ( !v8 )
                  goto LABEL_46;
                goto LABEL_45;
              }
              do
              {
                for ( i = 0; i < SDWORD2(pv); ++i )
                {
                  v21 = v18 + (int)v19 * i;
                  v30 = *((_BYTE *)ppvBits + 4 * v21 + 3);
                  if ( v30 )
                  {
                    v22 = 6;
                    if ( !gdiplusModule
                      || (v31 = *((_BYTE *)ppvBits + 4 * v21 + 2),
                          v23 = *((_BYTE *)ppvBits + 4 * v21 + 1),
                          v33 = *((_BYTE *)ppvBits + 4 * v21),
                          v40 = *((_QWORD *)PngGraphicFromMonochrome + 1),
                          v32 = v23,
                          (v24 = GetProcAddress(gdiplusModule, "GdipBitmapSetPixel")) == 0)
                      || (v22 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))v24)(
                                  v40,
                                  (unsigned int)v18,
                                  (unsigned int)i,
                                  v33 | ((v32 | ((v31 | (v30 << 8)) << 8)) << 8))) != 0 )
                    {
                      *((_DWORD *)PngGraphicFromMonochrome + 4) = v22;
                    }
                    v19 = (const unsigned __int16 *)DWORD1(pv);
                  }
                }
                ++v18;
              }
              while ( v18 < (int)v19 );
LABEL_36:
              if ( !PngGraphicFromMonochrome )
                goto LABEL_44;
              goto LABEL_37;
            }
          }
        }
LABEL_45:
        DeleteObject(v8);
LABEL_46:
        if ( !v7 )
        {
LABEL_48:
          v3 = v34;
          goto LABEL_50;
        }
LABEL_47:
        DeleteDC(v7);
        goto LABEL_48;
      }
    }
    else
    {
      v7 = 0;
      v8 = 0;
    }
LABEL_35:
    PngGraphicFromMonochrome = CreatePngGraphicFromMonochrome(a1);
    goto LABEL_36;
  }
LABEL_50:
  if ( gdiplusModule )
  {
    v27 = v39;
    v28 = GetProcAddress(gdiplusModule, "GdiplusShutdown");
    if ( v28 )
      ((void (__fastcall *)(__int64))v28)(v27);
  }
  return v3;
}

```

## disassembly

```asm
0x1801ac698  mov     [rsp-8+arg_10], rbx
0x1801ac69d  push    rbp
0x1801ac69e  push    rsi
0x1801ac69f  push    rdi
0x1801ac6a0  push    r12
0x1801ac6a2  push    r13
0x1801ac6a4  push    r14
0x1801ac6a6  push    r15
0x1801ac6a8  lea     rbp, [rsp-10h]
0x1801ac6ad  sub     rsp, 110h
0x1801ac6b4  mov     rax, cs:__security_cookie
0x1801ac6bb  xor     rax, rsp
0x1801ac6be  mov     [rbp+40h+var_38], rax
0x1801ac6c2  xor     r13d, r13d
0x1801ac6c5  mov     [rbp+40h+var_B8], rdx
0x1801ac6c9  xorps   xmm0, xmm0
0x1801ac6cc  mov     [rbp+40h+var_A8], r13
0x1801ac6d0  xorps   xmm1, xmm1
0x1801ac6d3  mov     [rbp+40h+var_A0], r13
0x1801ac6d7  mov     rbx, rcx
0x1801ac6da  mov     [rsp+140h+var_C8], r13
0x1801ac6df  mov     rcx, cs:gdiplusModule; hModule
0x1801ac6e6  mov     edi, 80004005h
0x1801ac6eb  mov     [rsp+140h+var_FC], edi
0x1801ac6ef  mov     esi, 1
0x1801ac6f4  mov     [rbp+40h+var_B0], esi
0x1801ac6f7  movups  xmmword ptr [rbp+40h+var_48.Data1], xmm0
0x1801ac6fb  movups  [rsp+140h+pv], xmm1
0x1801ac700  movups  [rsp+140h+var_E0], xmm1
0x1801ac705  movups  xmmword ptr [rbp+40h+piconinfo.fIcon], xmm0
0x1801ac709  movups  xmmword ptr [rbp+40h+piconinfo.hbmMask], xmm0
0x1801ac70d  test    rcx, rcx
0x1801ac710  jz      short loc_1801AC735
0x1801ac712  lea     rdx, aGdiplusstartup; "GdiplusStartup"
0x1801ac719  call    cs:__imp_GetProcAddress
0x1801ac71f  test    rax, rax
0x1801ac722  jz      short loc_1801AC735
0x1801ac724  xor     r8d, r8d
0x1801ac727  lea     rdx, [rbp+40h+var_B0]
0x1801ac72b  lea     rcx, [rsp+140h+var_C8]
0x1801ac730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ac735  lea     rdx, [rbp+40h+piconinfo]; piconinfo
0x1801ac739  mov     rcx, rbx; hIcon
0x1801ac73c  call    cs:__imp_GetIconInfo
0x1801ac742  test    eax, eax
0x1801ac744  jz      loc_1801ACAC3
0x1801ac74a  mov     rcx, [rbp+40h+piconinfo.hbmColor]; h
0x1801ac74e  mov     r15d, 6
0x1801ac754  test    rcx, rcx
0x1801ac757  jz      loc_1801ACA1F
0x1801ac75d  lea     r14d, [r15+1Ah]
0x1801ac761  mov     edx, r14d; c
0x1801ac764  lea     r8, [rsp+140h+pv]; pv
0x1801ac769  call    cs:__imp_GetObjectW
0x1801ac76f  test    eax, eax
0x1801ac771  jz      loc_1801ACA1F
0x1801ac777  cmp     word ptr [rsp+140h+var_E0+2], r14w
0x1801ac77d  jnz     loc_1801ACA1F
0x1801ac783  cmp     word ptr [rsp+140h+var_E0], si
0x1801ac788  jnz     loc_1801ACA1F
0x1801ac78e  xor     ecx, ecx; hdc
0x1801ac790  call    cs:__imp_CreateCompatibleDC
0x1801ac796  mov     rdi, rax
0x1801ac799  test    rax, rax
0x1801ac79c  jz      loc_1801ACABE
0x1801ac7a2  xor     eax, eax
0x1801ac7a4  mov     [rsp+140h+offset], r13d; offset
0x1801ac7a9  mov     qword ptr [rbp+40h+pbmi.bmiHeader.biClrImportant], rax
0x1801ac7ad  lea     r9, [rsp+140h+ppvBits]; ppvBits
0x1801ac7b2  mov     eax, dword ptr [rsp+140h+pv+4]
0x1801ac7b6  lea     rdx, [rbp+40h+pbmi]; pbmi
0x1801ac7ba  xorps   xmm0, xmm0
0x1801ac7bd  mov     [rbp+40h+pbmi.bmiHeader.biSize], 28h ; '('
0x1801ac7c4  movups  xmmword ptr [rbp+40h+pbmi.bmiHeader.biWidth], xmm0
0x1801ac7c8  mov     [rbp+40h+pbmi.bmiHeader.biWidth], eax
0x1801ac7cb  xor     r8d, r8d; usage
0x1801ac7ce  mov     eax, dword ptr [rsp+140h+pv+8]
0x1801ac7d2  mov     rcx, rdi; hdc
0x1801ac7d5  neg     eax
0x1801ac7d7  mov     qword ptr [rbp+40h+pbmi.bmiHeader.biPlanes], 200001h
0x1801ac7df  mov     [rbp+40h+pbmi.bmiHeader.biHeight], eax
0x1801ac7e2  movups  xmmword ptr [rbp+40h+pbmi.bmiHeader.biSizeImage], xmm0
0x1801ac7e6  mov     [rsp+140h+ppvBits], r13
0x1801ac7eb  mov     [rsp+140h+hSection], r13; hSection
0x1801ac7f0  call    cs:__imp_CreateDIBSection
0x1801ac7f6  mov     r12, rax
0x1801ac7f9  test    rax, rax
0x1801ac7fc  jz      loc_1801ACAAF
0x1801ac802  mov     r9d, dword ptr [rsp+140h+pv+8]; cLines
0x1801ac807  lea     rax, [rbp+40h+pbmi]
0x1801ac80b  mov     rdx, [rbp+40h+piconinfo.hbmColor]; hbm
0x1801ac80f  xor     r8d, r8d; start
0x1801ac812  mov     [rsp+140h+usage], r13d; usage
0x1801ac817  mov     rcx, rdi; hdc
0x1801ac81a  mov     qword ptr [rsp+140h+offset], rax; lpbmi
0x1801ac81f  mov     rax, [rsp+140h+ppvBits]
0x1801ac824  mov     [rsp+140h+hSection], rax; lpvBits
0x1801ac829  call    cs:__imp_GetDIBits
0x1801ac82f  test    eax, eax
0x1801ac831  jz      loc_1801ACAA1
0x1801ac837  mov     r9d, dword ptr [rsp+140h+pv+4]
0x1801ac83c  mov     edx, r13d
0x1801ac83f  test    r9d, r9d
0x1801ac842  jle     loc_1801ACA25
0x1801ac848  mov     r8d, dword ptr [rsp+140h+pv+8]
0x1801ac84d  mov     r10, [rsp+140h+ppvBits]
0x1801ac852  mov     ecx, r13d
0x1801ac855  test    r8d, r8d
0x1801ac858  jle     short loc_1801AC872
0x1801ac85a  mov     eax, ecx
0x1801ac85c  imul    eax, r8d
0x1801ac860  add     eax, edx
0x1801ac862  cdqe
0x1801ac864  cmp     [r10+rax*4+3], r13b
0x1801ac869  jnz     short loc_1801AC87E
0x1801ac86b  add     ecx, esi
0x1801ac86d  cmp     ecx, r8d
0x1801ac870  jl      short loc_1801AC85A
0x1801ac872  add     edx, esi
0x1801ac874  cmp     edx, r9d
0x1801ac877  jl      short loc_1801AC852
0x1801ac879  jmp     loc_1801ACA25
0x1801ac87e  mov     rcx, cs:gdiplusModule; hModule
0x1801ac885  test    rcx, rcx
0x1801ac888  jz      loc_1801ACAA1
0x1801ac88e  lea     rdx, aGdipalloc; "GdipAlloc"
0x1801ac895  call    cs:__imp_GetProcAddress
0x1801ac89b  test    rax, rax
0x1801ac89e  jz      loc_1801ACAA1
0x1801ac8a4  mov     ecx, 18h
0x1801ac8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ac8ae  mov     rbx, rax
0x1801ac8b1  test    rax, rax
0x1801ac8b4  jz      loc_1801ACAA1
0x1801ac8ba  mov     rcx, cs:gdiplusModule; hModule
0x1801ac8c1  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x1801ac8c8  mov     r14d, dword ptr [rsp+140h+pv+8]
0x1801ac8cd  mov     esi, r15d
0x1801ac8d0  mov     r13d, dword ptr [rsp+140h+pv+4]
0x1801ac8d5  mov     [rbx], rax
0x1801ac8d8  mov     [rsp+140h+var_D0], 0
0x1801ac8e1  test    rcx, rcx
0x1801ac8e4  jz      short loc_1801AC921
0x1801ac8e6  lea     rdx, aGdipcreatebitm_0; "GdipCreateBitmapFromScan0"
0x1801ac8ed  call    cs:__imp_GetProcAddress
0x1801ac8f3  test    rax, rax
0x1801ac8f6  jz      short loc_1801AC921
0x1801ac8f8  lea     rcx, [rsp+140h+var_D0]
0x1801ac8fd  mov     r9d, 26200Ah
0x1801ac903  mov     qword ptr [rsp+140h+offset], rcx
0x1801ac908  xor     r8d, r8d
0x1801ac90b  mov     ecx, r13d
0x1801ac90e  mov     [rsp+140h+hSection], 0
0x1801ac917  mov     edx, r14d
0x1801ac91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ac91f  mov     esi, eax
0x1801ac921  mov     rax, [rsp+140h+var_D0]
0x1801ac926  xor     r13d, r13d
0x1801ac929  mov     [rbx+8], rax
0x1801ac92d  mov     r14d, r13d
0x1801ac930  mov     [rbx+10h], esi
0x1801ac933  mov     ecx, dword ptr [rsp+140h+pv+4]
0x1801ac937  test    ecx, ecx
0x1801ac939  jle     loc_1801ACA35
0x1801ac93f  mov     esi, r13d
0x1801ac942  cmp     dword ptr [rsp+140h+pv+8], r13d
0x1801ac947  jle     loc_1801ACA11
0x1801ac94d  mov     eax, esi
0x1801ac94f  imul    eax, ecx
0x1801ac952  add     eax, r14d
0x1801ac955  movsxd  rdx, eax
0x1801ac958  mov     rax, [rsp+140h+ppvBits]
0x1801ac95d  mov     r8b, [rax+rdx*4+3]
0x1801ac962  mov     [rsp+140h+var_100], r8b
0x1801ac967  test    r8b, r8b
0x1801ac96a  jz      loc_1801ACA05
0x1801ac970  mov     rcx, cs:gdiplusModule; hModule
0x1801ac977  mov     r13d, r15d
0x1801ac97a  test    rcx, rcx
0x1801ac97d  jz      short loc_1801AC9FA
0x1801ac97f  mov     r8b, [rax+rdx*4+2]
0x1801ac984  mov     [rsp+140h+var_FF], r8b
0x1801ac989  mov     r8b, [rax+rdx*4+1]
0x1801ac98e  mov     al, [rax+rdx*4]
0x1801ac991  lea     rdx, aGdipbitmapsetp; "GdipBitmapSetPixel"
0x1801ac998  mov     [rsp+140h+var_FD], al
0x1801ac99c  mov     rax, [rbx+8]
0x1801ac9a0  mov     [rbp+40h+var_C0], rax
0x1801ac9a4  mov     [rsp+140h+var_FE], r8b
0x1801ac9a9  call    cs:__imp_GetProcAddress
0x1801ac9af  mov     r10, rax
0x1801ac9b2  test    rax, rax
0x1801ac9b5  jz      short loc_1801AC9FA
0x1801ac9b7  movzx   eax, [rsp+140h+var_FF]
0x1801ac9bc  mov     r8d, esi
0x1801ac9bf  movzx   r9d, [rsp+140h+var_100]
0x1801ac9c5  mov     edx, r14d
0x1801ac9c8  mov     rcx, [rbp+40h+var_C0]
0x1801ac9cc  shl     r9d, 8
0x1801ac9d0  or      r9d, eax
0x1801ac9d3  movzx   eax, [rsp+140h+var_FE]
0x1801ac9d8  shl     r9d, 8
0x1801ac9dc  or      r9d, eax
0x1801ac9df  movzx   eax, [rsp+140h+var_FD]
0x1801ac9e4  shl     r9d, 8
0x1801ac9e8  or      r9d, eax
0x1801ac9eb  mov     rax, r10
0x1801ac9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ac9f3  mov     r13d, eax
0x1801ac9f6  test    eax, eax
0x1801ac9f8  jz      short loc_1801AC9FE
0x1801ac9fa  mov     [rbx+10h], r13d
0x1801ac9fe  mov     ecx, dword ptr [rsp+140h+pv+4]
0x1801aca02  xor     r13d, r13d
0x1801aca05  inc     esi
0x1801aca07  cmp     esi, dword ptr [rsp+140h+pv+8]
0x1801aca0b  jl      loc_1801AC94D
0x1801aca11  inc     r14d
0x1801aca14  cmp     r14d, ecx
0x1801aca17  jl      loc_1801AC93F
0x1801aca1d  jmp     short loc_1801ACA30
0x1801aca1f  mov     rdi, r13
0x1801aca22  mov     r12, r13
0x1801aca25  mov     rcx, rbx; HICON
0x1801aca28  call    ?CreatePngGraphicFromMonochrome@@YAPEAVBitmap@Gdiplus@@PEAUHICON__@@@Z; CreatePngGraphicFromMonochrome(HICON__ *)
0x1801aca2d  mov     rbx, rax
0x1801aca30  test    rbx, rbx
0x1801aca33  jz      short loc_1801ACA9C
0x1801aca35  lea     rdx, [rbp+40h+var_48]; struct _GUID *
0x1801aca39  call    ?GetEncoderClsid@@YAHPEBGPEAU_GUID@@@Z; GetEncoderClsid(ushort const *,_GUID *)
0x1801aca3e  test    eax, eax
0x1801aca40  jz      short loc_1801ACA89
0x1801aca42  mov     rcx, cs:gdiplusModule; hModule
0x1801aca49  test    rcx, rcx
0x1801aca4c  jz      short loc_1801ACA85
0x1801aca4e  mov     rsi, [rbx+8]
0x1801aca52  lea     rdx, aGdipsaveimaget; "GdipSaveImageToFile"
0x1801aca59  call    cs:__imp_GetProcAddress
0x1801aca5f  test    rax, rax
0x1801aca62  jz      short loc_1801ACA85
0x1801aca64  mov     rdx, [rbp+40h+var_B8]
0x1801aca68  lea     r8, [rbp+40h+var_48]
0x1801aca6c  xor     r9d, r9d
0x1801aca6f  mov     rcx, rsi
0x1801aca72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aca77  mov     r15d, eax
0x1801aca7a  test    eax, eax
0x1801aca7c  jnz     short loc_1801ACA85
0x1801aca7e  mov     [rsp+140h+var_FC], r13d
0x1801aca83  jmp     short loc_1801ACA89
0x1801aca85  mov     [rbx+10h], r15d
0x1801aca89  mov     rax, [rbx]
0x1801aca8c  mov     edx, 1
0x1801aca91  mov     rcx, rbx
0x1801aca94  mov     rax, [rax]
0x1801aca97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aca9c  test    r12, r12
0x1801aca9f  jz      short loc_1801ACAAA
0x1801acaa1  mov     rcx, r12; ho
0x1801acaa4  call    cs:__imp_DeleteObject
0x1801acaaa  test    rdi, rdi
0x1801acaad  jz      short loc_1801ACAB8
0x1801acaaf  mov     rcx, rdi; hdc
0x1801acab2  call    cs:__imp_DeleteDC
0x1801acab8  mov     edi, [rsp+140h+var_FC]
0x1801acabc  jmp     short loc_1801ACAC3
0x1801acabe  mov     edi, 80004005h
0x1801acac3  mov     rcx, cs:gdiplusModule; hModule
0x1801acaca  test    rcx, rcx
0x1801acacd  jz      short loc_1801ACAEE
0x1801acacf  mov     rbx, [rsp+140h+var_C8]
0x1801acad4  lea     rdx, aGdiplusshutdow; "GdiplusShutdown"
0x1801acadb  call    cs:__imp_GetProcAddress
0x1801acae1  test    rax, rax
0x1801acae4  jz      short loc_1801ACAEE
0x1801acae6  mov     rcx, rbx
0x1801acae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801acaee  mov     eax, edi
0x1801acaf0  mov     rcx, [rbp+40h+var_38]
0x1801acaf4  xor     rcx, rsp; StackCookie
0x1801acaf7  call    __security_check_cookie
0x1801acafc  mov     rbx, [rsp+140h+arg_10]
0x1801acb04  add     rsp, 110h
0x1801acb0b  pop     r15
0x1801acb0d  pop     r14
0x1801acb0f  pop     r13
0x1801acb11  pop     r12
0x1801acb13  pop     rdi
0x1801acb14  pop     rsi
0x1801acb15  pop     rbp
0x1801acb16  retn
```
