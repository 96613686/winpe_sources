# ConvertMFVideoFormatToVIH3(tagVIDEOINFOHEADER *,_MFVIDEOFORMAT *)

- ea: `0x1800131e8`
- end: `0x18001344e`
- name: `?ConvertMFVideoFormatToVIH3@@YAJPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(struct tagVIDEOINFOHEADER *, struct _MFVIDEOFORMAT *)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012cd0`
- `0x180012df8`
- `0x180012e50`
- `0x180013fa0`
- `0x1800149ac`

## callees

- `0x1800131e8`
- `0x180013454`
- `0x180013508`
- `0x180045805`

## pseudocode

```c
__int64 __fastcall ConvertMFVideoFormatToVIH3(struct tagVIDEOINFOHEADER *a1, struct _MFVIDEOFORMAT *a2)
{
  unsigned int v4; // ebp
  LONG dwWidth; // r14d
  LONG dwHeight; // esi
  unsigned int Data1; // ecx
  DWORD v8; // r8d
  WORD v9; // ax
  BOOL v10; // edx
  int v11; // ecx
  DWORD v12; // eax
  DWORD PaletteEntries; // eax
  unsigned int v14; // eax
  int v16; // ecx
  int v17; // eax
  DWORD Format; // eax
  _BYTE v19[56]; // [rsp+30h] [rbp-38h] BYREF
  int v20; // [rsp+70h] [rbp+8h] BYREF
  int v21; // [rsp+80h] [rbp+18h] BYREF
  DWORD v22; // [rsp+88h] [rbp+20h] BYREF

  if ( a1 && a2 )
  {
    v4 = 0;
    a1->rcTarget.left = 0;
    a1->rcTarget.right = a2->videoInfo.dwWidth;
    a1->rcTarget.top = 0;
    a1->rcTarget.bottom = a2->videoInfo.dwHeight;
    a1->rcSource = a1->rcTarget;
    RateToAverageTimePerFrame(
      a2->videoInfo.FramesPerSecond.Numerator,
      a2->videoInfo.FramesPerSecond.Denominator,
      &a1->AvgTimePerFrame);
    *(_QWORD *)&a1->bmiHeader.biXPelsPerMeter = 0;
    a1->bmiHeader.biSize = 40;
    dwWidth = a2->videoInfo.dwWidth;
    a1->bmiHeader.biWidth = dwWidth;
    dwHeight = a2->videoInfo.dwHeight;
    a1->bmiHeader.biHeight = dwHeight;
    a1->dwBitRate = a2->compressedInfo.AvgBitrate;
    Data1 = a2->guidFormat.Data1;
    v22 = 0;
    v21 = 0;
    v20 = 0;
    GetCompressionAndBitCount(Data1, (unsigned int)&v22, (unsigned int)&v21, (unsigned int)&v20, (__int64)v19);
    v8 = v22;
    v9 = v21;
    a1->bmiHeader.biPlanes = v20;
    a1->bmiHeader.biBitCount = v9;
    v10 = v8 == 842094158
       || v8 == 961893977
       || v8 == 842094169
       || v8 == 825316942
       || v8 == 808596553
       || v8 == 1448433993;
    v11 = -dwHeight;
    if ( dwHeight > 0 )
      v11 = dwHeight;
    if ( v10 )
      v12 = dwWidth * v11 * v9 / 8;
    else
      v12 = 4 * v11 * ((dwWidth * v9 / 8 + 3) / 4);
    a1->bmiHeader.biSizeImage = v12;
    if ( v8 == 808530550 )
    {
      v16 = -dwWidth;
      if ( dwWidth > 0 )
        v16 = dwWidth;
      v17 = -dwHeight;
      if ( dwHeight > 0 )
        v17 = dwHeight;
      a1->bmiHeader.biSizeImage = (v17 * ((v16 + 47) / 48)) << 7;
    }
    a1->bmiHeader.biCompression = v8;
    *(_QWORD *)&a1->bmiHeader.biClrUsed = a2->surfaceInfo.PaletteEntries;
    if ( v8 > 3 )
      goto LABEL_11;
    if ( (a2->videoInfo.VideoFlags & 0x80000) == 0 )
      a1->bmiHeader.biHeight = -dwHeight;
    if ( v8 == 3 )
    {
      Format = a2->surfaceInfo.Format;
      if ( Format == 23 || Format == -466162821 )
      {
        a1[1].rcSource.left = 63488;
        a1[1].rcSource.top = 2016;
        goto LABEL_38;
      }
      if ( Format == 24 || Format == -466162820 )
      {
        a1[1].rcSource.left = 31744;
        a1[1].rcSource.top = 992;
LABEL_38:
        a1[1].rcSource.right = 31;
      }
    }
    else
    {
LABEL_11:
      PaletteEntries = a2->surfaceInfo.PaletteEntries;
      if ( PaletteEntries > 0x100 )
      {
        return (unsigned int)-1072875852;
      }
      else
      {
        v14 = 4 * PaletteEntries;
        if ( v14 )
          memcpy_0(&a1[1], a2->surfaceInfo.Palette, v14);
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v4;
}

```

## disassembly

```asm
0x1800131e8  push    rbx
0x1800131ea  push    rbp
0x1800131eb  push    rsi
0x1800131ec  push    rdi
0x1800131ed  push    r14
0x1800131ef  sub     rsp, 40h
0x1800131f3  mov     rdi, rdx
0x1800131f6  mov     rbx, rcx
0x1800131f9  test    rcx, rcx
0x1800131fc  jz      loc_180013378
0x180013202  test    rdx, rdx
0x180013205  jz      loc_180013378
0x18001320b  xor     ebp, ebp
0x18001320d  lea     r8, [rcx+28h]
0x180013211  mov     [rcx+10h], ebp
0x180013214  mov     eax, [rdx+8]
0x180013217  mov     [rcx+18h], eax
0x18001321a  mov     [rcx+14h], ebp
0x18001321d  mov     eax, [rdx+0Ch]
0x180013220  mov     [rcx+1Ch], eax
0x180013223  movups  xmm0, xmmword ptr [rcx+10h]
0x180013227  movdqu  xmmword ptr [rcx], xmm0
0x18001322b  mov     edx, [rdx+34h]
0x18001322e  mov     ecx, [rdi+30h]
0x180013231  call    RateToAverageTimePerFrame
0x180013236  mov     [rbx+48h], rbp
0x18001323a  lea     r9, [rsp+68h+arg_0]
0x18001323f  mov     dword ptr [rbx+30h], 28h ; '('
0x180013246  lea     r8, [rsp+68h+arg_10]
0x18001324e  mov     r14d, [rdi+8]
0x180013252  lea     rdx, [rsp+68h+arg_18]
0x18001325a  mov     [rbx+34h], r14d
0x18001325e  mov     esi, [rdi+0Ch]
0x180013261  mov     [rbx+38h], esi
0x180013264  mov     eax, [rdi+88h]
0x18001326a  mov     [rbx+20h], eax
0x18001326d  lea     rax, [rsp+68h+var_38]
0x180013272  mov     ecx, [rdi+78h]
0x180013275  mov     [rsp+68h+var_48], rax
0x18001327a  mov     [rsp+68h+arg_18], ebp
0x180013281  mov     [rsp+68h+arg_10], ebp
0x180013288  mov     [rsp+68h+arg_0], ebp
0x18001328c  call    GetCompressionAndBitCount
0x180013291  movzx   ecx, word ptr [rsp+68h+arg_0]
0x180013296  mov     r8d, [rsp+68h+arg_18]
0x18001329e  mov     eax, [rsp+68h+arg_10]
0x1800132a5  mov     [rbx+3Ch], cx
0x1800132a9  mov     [rbx+3Eh], ax
0x1800132ad  cmp     r8d, 3231564Eh
0x1800132b4  jnz     short loc_18001332D
0x1800132b6  mov     edx, 1
0x1800132bb  mov     ecx, esi
0x1800132bd  movzx   eax, ax
0x1800132c0  neg     ecx
0x1800132c2  mov     r9d, 8
0x1800132c8  cmovs   ecx, esi
0x1800132cb  test    edx, edx
0x1800132cd  jz      loc_18001337F
0x1800132d3  imul    eax, ecx
0x1800132d6  imul    eax, r14d
0x1800132da  cdq
0x1800132db  idiv    r9d
0x1800132de  mov     [rbx+44h], eax
0x1800132e1  cmp     r8d, 30313276h
0x1800132e8  jz      loc_18001339F
0x1800132ee  mov     [rbx+40h], r8d
0x1800132f2  mov     eax, [rdi+0A4h]
0x1800132f8  mov     [rbx+50h], eax
0x1800132fb  mov     [rbx+54h], ebp
0x1800132fe  cmp     r8d, 3
0x180013302  jbe     loc_1800133D1
0x180013308  mov     eax, [rdi+0A4h]
0x18001330e  cmp     eax, 100h
0x180013313  ja      short loc_180013371
0x180013315  shl     eax, 2
0x180013318  test    eax, eax
0x18001331a  jnz     loc_180013436
0x180013320  mov     eax, ebp
0x180013322  add     rsp, 40h
0x180013326  pop     r14
0x180013328  pop     rdi
0x180013329  pop     rsi
0x18001332a  pop     rbp
0x18001332b  pop     rbx
0x18001332c  retn
0x18001332d  cmp     r8d, 39555659h
0x180013334  jz      short loc_1800132B6
0x180013336  cmp     r8d, 32315659h
0x18001333d  jz      loc_1800132B6
0x180013343  cmp     r8d, 3131564Eh
0x18001334a  jz      loc_1800132B6
0x180013350  cmp     r8d, 30323449h
0x180013357  jz      loc_1800132B6
0x18001335d  cmp     r8d, 56555949h
0x180013364  jz      loc_1800132B6
0x18001336a  xor     edx, edx
0x18001336c  jmp     loc_1800132BB
0x180013371  mov     ebp, 0C00D36B4h
0x180013376  jmp     short loc_180013320
0x180013378  mov     ebp, 80004003h
0x18001337d  jmp     short loc_180013320
0x18001337f  imul    eax, r14d
0x180013383  cdq
0x180013384  idiv    r9d
0x180013387  mov     r9d, 4
0x18001338d  add     eax, 3
0x180013390  cdq
0x180013391  idiv    r9d
0x180013394  imul    eax, ecx
0x180013397  shl     eax, 2
0x18001339a  jmp     loc_1800132DE
0x18001339f  mov     ecx, r14d
0x1800133a2  mov     eax, 2AAAAAABh
0x1800133a7  neg     ecx
0x1800133a9  cmovs   ecx, r14d
0x1800133ad  add     ecx, 2Fh ; '/'
0x1800133b0  imul    ecx
0x1800133b2  sar     edx, 3
0x1800133b5  mov     eax, edx
0x1800133b7  shr     eax, 1Fh
0x1800133ba  add     edx, eax
0x1800133bc  mov     eax, esi
0x1800133be  neg     eax
0x1800133c0  cmovs   eax, esi
0x1800133c3  imul    edx, eax
0x1800133c6  shl     edx, 7
0x1800133c9  mov     [rbx+44h], edx
0x1800133cc  jmp     loc_1800132EE
0x1800133d1  mov     eax, [rdi+70h]
0x1800133d4  bt      rax, 13h
0x1800133d9  jb      short loc_1800133E0
0x1800133db  neg     esi
0x1800133dd  mov     [rbx+38h], esi
0x1800133e0  cmp     r8d, 3
0x1800133e4  jnz     loc_180013308
0x1800133ea  mov     eax, [rdi+0A0h]
0x1800133f0  cmp     eax, 17h
0x1800133f3  jz      short loc_18001341C
0x1800133f5  cmp     eax, 0E436EB7Bh
0x1800133fa  jz      short loc_18001341C
0x1800133fc  cmp     eax, 18h
0x1800133ff  jz      short loc_18001340C
0x180013401  cmp     eax, 0E436EB7Ch
0x180013406  jnz     loc_180013320
0x18001340c  mov     dword ptr [rbx+58h], 7C00h
0x180013413  mov     dword ptr [rbx+5Ch], 3E0h
0x18001341a  jmp     short loc_18001342A
0x18001341c  mov     dword ptr [rbx+58h], 0F800h
0x180013423  mov     dword ptr [rbx+5Ch], 7E0h
0x18001342a  mov     dword ptr [rbx+60h], 1Fh
0x180013431  jmp     loc_180013320
0x180013436  mov     r8d, eax; Size
0x180013439  lea     rdx, [rdi+0A8h]; Src
0x180013440  lea     rcx, [rbx+58h]; void *
0x180013444  call    memcpy_0
0x180013449  jmp     loc_180013320
```
