# CopyOnWriteBitmap::CreateFromHICON(HICON__ *,CopyOnWriteBitmap * *)

- ea: `0x180008ffc`
- end: `0x18000930a`
- name: `?CreateFromHICON@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHICON__@@PEAPEAV1@@Z`
- size: `782`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008af0`

## callees

- `0x180007474`
- `0x180008ffc`
- `0x180009310`
- `0x18001ec80`
- `0x180025270`
- `0x180025ae8`
- `0x1800fe680`
- `0x1800ff04c`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800090e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800090e3`
- `USER32!GetIconInfo` at `0x180009041`
- `USER32!GetIconInfo` at `0x180009041`
- `USER32!GetDC` at `0x180009250`
- `USER32!GetDC` at `0x180009250`
- `USER32!ReleaseDC` at `0x1800091fa`
- `USER32!ReleaseDC` at `0x1800091fa`
- `GDI32!GetStockObject` at `0x180009064`
- `GDI32!GetStockObject` at `0x180009064`
- `GDI32!GetDIBits` at `0x18000911a`
- `GDI32!GetDIBits` at `0x18000929c`
- `GDI32!GetDIBits` at `0x18000911a`
- `GDI32!GetDIBits` at `0x18000929c`
- `GDI32!DeleteObject` at `0x18000908e`
- `GDI32!DeleteObject` at `0x18000909e`
- `GDI32!DeleteObject` at `0x18000908e`
- `GDI32!DeleteObject` at `0x18000909e`

## pseudocode

```c
__int64 __fastcall CopyOnWriteBitmap::CreateFromHICON(HICON a1, _QWORD *a2)
{
  HGDIOBJ StockObject; // rax
  unsigned int v4; // ebx
  _DWORD *lpvBits; // rsi
  __int64 v7; // rcx
  unsigned int v8; // ecx
  int v9; // r12d
  _DWORD *v10; // r10
  unsigned int v11; // r15d
  unsigned int v12; // r9d
  _DWORD *v13; // r11
  _DWORD *v14; // rax
  _DWORD *v15; // rdx
  unsigned int v16; // r8d
  __int64 v17; // rdi
  __int64 v18; // rcx
  int v19; // eax
  unsigned int v20; // eax
  HDC DC; // r14
  LONG biHeight; // ecx
  LONG v23; // ecx
  unsigned __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned __int64 v26; // rcx
  ICONINFO piconinfo; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+70h] [rbp-90h]
  struct tagBITMAPINFO bmi; // [rsp+80h] [rbp-80h] BYREF

  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( !GetIconInfo(a1, &piconinfo) )
    return 2;
  if ( piconinfo.fIcon && piconinfo.hbmColor )
  {
    StockObject = GetStockObject(15);
    v4 = CopyOnWriteBitmap::CreateFromHBITMAP(piconinfo.hbmColor, StockObject, a2);
    if ( !v4 )
    {
      if ( *a2 )
      {
        v20 = CopyOnWriteBitmap::ConvertFormat(*a2, 2498570, 1, 0, 0, 0);
        MapHRESULTToGpStatus(v20);
      }
      if ( !piconinfo.hbmMask )
        goto LABEL_7;
      v4 = 7;
      DC = GetDC(0);
      if ( DC )
      {
        memset_0(&bmi.bmiHeader.biWidth, 0, 0x424u);
        bmi.bmiHeader.biSize = 40;
        if ( GetDIBits(DC, piconinfo.hbmMask, 0, 0, 0, &bmi, 0) )
        {
          biHeight = -bmi.bmiHeader.biHeight;
          bmi.bmiHeader.biSize = 40;
          if ( bmi.bmiHeader.biHeight > 0 )
            biHeight = bmi.bmiHeader.biHeight;
          v23 = -biHeight;
          v24 = 4LL * (unsigned int)bmi.bmiHeader.biWidth;
          bmi.bmiHeader.biHeight = v23;
          *(_QWORD *)&bmi.bmiHeader.biPlanes = 2097153;
          bmi.bmiHeader.biSizeImage = 0;
          *(_QWORD *)&bmi.bmiHeader.biClrUsed = 0;
          if ( v24 > 0xFFFFFFFF )
            goto LABEL_39;
          v25 = -v23;
          if ( v23 > 0 )
            v25 = v23;
          v26 = (unsigned int)v24 * (unsigned __int64)v25;
          if ( v26 <= 0xFFFFFFFF )
          {
            lpvBits = HeapAlloc(GpRuntime::GpMemHeap, 0, (unsigned int)v26);
            if ( lpvBits )
            {
              if ( GetDIBits(DC, piconinfo.hbmMask, 0, -bmi.bmiHeader.biHeight, lpvBits, &bmi, 0) )
              {
                v7 = *a2;
                v28 = 0;
                v29 = 0;
                v4 = CopyOnWriteBitmap::LockBits(v7, 0, 3, 2498570, &v28);
                if ( !v4 )
                {
                  v8 = DWORD1(v28);
                  v9 = 4 * bmi.bmiHeader.biWidth;
                  if ( DWORD1(v28) )
                  {
                    v10 = (_DWORD *)v29;
                    v11 = 0;
                    v12 = v28;
                    v13 = lpvBits;
                    do
                    {
                      v14 = v10;
                      v15 = v13;
                      v16 = 0;
                      if ( v12 )
                      {
                        do
                        {
                          if ( *v15 )
                          {
                            *v14 = 0;
                            v12 = v28;
                          }
                          ++v14;
                          ++v15;
                          ++v16;
                        }
                        while ( v16 < v12 );
                        v8 = DWORD1(v28);
                      }
                      ++v11;
                      v10 = (_DWORD *)((char *)v10 + SDWORD2(v28));
                      v13 = (_DWORD *)((char *)v13 + v9);
                    }
                    while ( v11 < v8 );
                  }
                  v17 = *a2;
                  v18 = *(_QWORD *)(v17 + 88);
                  if ( v18 )
                  {
                    v19 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v18 + 48LL))(v18, &v28);
                    --*(_DWORD *)(v17 + 60);
                    if ( v19 < 0 )
                      MapHRESULTToGpStatus((unsigned int)v19);
                  }
                }
              }
              GpFree(lpvBits);
            }
            else
            {
              v4 = 3;
            }
          }
          else
          {
LABEL_39:
            v4 = 11;
          }
        }
        ReleaseDC(0, DC);
      }
    }
  }
  else
  {
    v4 = 2;
  }
  if ( piconinfo.hbmMask )
    DeleteObject(piconinfo.hbmMask);
LABEL_7:
  if ( piconinfo.hbmColor )
    DeleteObject(piconinfo.hbmColor);
  return v4;
}

```

## disassembly

```asm
0x180008ffc  mov     [rsp-8+arg_10], rbx
0x180009001  push    rbp
0x180009002  push    rsi
0x180009003  push    rdi
0x180009004  push    r12
0x180009006  push    r13
0x180009008  push    r14
0x18000900a  push    r15
0x18000900c  lea     rbp, [rsp-3C0h]
0x180009014  sub     rsp, 4C0h
0x18000901b  mov     rax, cs:__security_cookie
0x180009022  xor     rax, rsp
0x180009025  mov     [rbp+3F0h+var_40], rax
0x18000902c  xorps   xmm0, xmm0
0x18000902f  mov     rdi, rdx
0x180009032  lea     rdx, [rsp+4F0h+piconinfo]; piconinfo
0x180009037  movups  xmmword ptr [rsp+4F0h+piconinfo.fIcon], xmm0
0x18000903c  movups  xmmword ptr [rsp+4F0h+piconinfo.hbmMask], xmm0
0x180009041  call    cs:__imp_GetIconInfo
0x180009047  xor     r13d, r13d
0x18000904a  test    eax, eax
0x18000904c  jz      loc_180009300
0x180009052  cmp     [rsp+4F0h+piconinfo.fIcon], r13d
0x180009057  jz      short loc_1800090D0
0x180009059  cmp     [rsp+4F0h+piconinfo.hbmColor], r13
0x18000905e  jz      short loc_1800090D0
0x180009060  lea     ecx, [r13+0Fh]; i
0x180009064  call    cs:__imp_GetStockObject
0x18000906a  mov     rcx, [rsp+4F0h+piconinfo.hbmColor]
0x18000906f  mov     r8, rdi
0x180009072  mov     rdx, rax
0x180009075  call    ?CreateFromHBITMAP@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHBITMAP__@@PEAUHPALETTE__@@PEAPEAV1@@Z; CopyOnWriteBitmap::CreateFromHBITMAP(HBITMAP__ *,HPALETTE__ *,CopyOnWriteBitmap * *)
0x18000907a  mov     ebx, eax
0x18000907c  test    eax, eax
0x18000907e  jz      loc_18000920C
0x180009084  mov     rcx, [rsp+4F0h+piconinfo.hbmMask]; ho
0x180009089  test    rcx, rcx
0x18000908c  jz      short loc_180009094
0x18000908e  call    cs:__imp_DeleteObject
0x180009094  mov     rcx, [rsp+4F0h+piconinfo.hbmColor]; ho
0x180009099  test    rcx, rcx
0x18000909c  jz      short loc_1800090A4
0x18000909e  call    cs:__imp_DeleteObject
0x1800090a4  mov     eax, ebx
0x1800090a6  mov     rcx, [rbp+3F0h+var_40]
0x1800090ad  xor     rcx, rsp; StackCookie
0x1800090b0  call    __security_check_cookie
0x1800090b5  mov     rbx, [rsp+4F0h+arg_10]
0x1800090bd  add     rsp, 4C0h
0x1800090c4  pop     r15
0x1800090c6  pop     r14
0x1800090c8  pop     r13
0x1800090ca  pop     r12
0x1800090cc  pop     rdi
0x1800090cd  pop     rsi
0x1800090ce  pop     rbp
0x1800090cf  retn
0x1800090d0  mov     ebx, 2
0x1800090d5  jmp     short loc_180009084
0x1800090d7  mov     r8d, ecx; dwBytes
0x1800090da  xor     edx, edx; dwFlags
0x1800090dc  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800090e3  call    cs:__imp_HeapAlloc
0x1800090e9  mov     rsi, rax
0x1800090ec  test    rax, rax
0x1800090ef  jz      loc_180009205
0x1800090f5  mov     r9d, [rbp+3F0h+bmi.bmiHeader.biHeight]
0x1800090f9  lea     rax, [rbp+3F0h+bmi]
0x1800090fd  mov     rdx, [rsp+4F0h+piconinfo.hbmMask]; hbm
0x180009102  neg     r9d; cLines
0x180009105  mov     [rsp+4F0h+usage], r13d; usage
0x18000910a  xor     r8d, r8d; start
0x18000910d  mov     [rsp+4F0h+lpbmi], rax; lpbmi
0x180009112  mov     rcx, r14; hdc
0x180009115  mov     [rsp+4F0h+lpvBits], rsi; lpvBits
0x18000911a  call    cs:__imp_GetDIBits
0x180009120  test    eax, eax
0x180009122  jz      loc_1800091ED
0x180009128  mov     rcx, [rdi]
0x18000912b  lea     rax, [rsp+4F0h+var_490]
0x180009130  xorps   xmm0, xmm0
0x180009133  mov     [rsp+4F0h+lpvBits], rax
0x180009138  xor     edx, edx
0x18000913a  mov     r9d, r15d
0x18000913d  movups  [rsp+4F0h+var_490], xmm0
0x180009142  movups  [rsp+4F0h+var_480], xmm0
0x180009147  lea     r8d, [rdx+3]
0x18000914b  call    ?LockBits@CopyOnWriteBitmap@@AEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; CopyOnWriteBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x180009150  mov     ebx, eax
0x180009152  test    eax, eax
0x180009154  jnz     loc_1800091ED
0x18000915a  mov     eax, [rbp+3F0h+bmi.bmiHeader.biWidth]
0x18000915d  mov     ecx, dword ptr [rsp+4F0h+var_490+4]
0x180009161  lea     r12d, ds:0[rax*4]
0x180009169  test    ecx, ecx
0x18000916b  jz      short loc_1800091C2
0x18000916d  mov     r10, qword ptr [rsp+4F0h+var_480]
0x180009172  mov     r15d, r13d
0x180009175  mov     r9d, dword ptr [rsp+4F0h+var_490]
0x18000917a  mov     r11, rsi
0x18000917d  mov     rax, r10
0x180009180  mov     rdx, r11
0x180009183  mov     r8d, r13d
0x180009186  test    r9d, r9d
0x180009189  jz      short loc_1800091AC
0x18000918b  cmp     [rdx], r13d
0x18000918e  jz      short loc_180009198
0x180009190  mov     [rax], r13d
0x180009193  mov     r9d, dword ptr [rsp+4F0h+var_490]
0x180009198  add     rax, 4
0x18000919c  add     rdx, 4
0x1800091a0  inc     r8d
0x1800091a3  cmp     r8d, r9d
0x1800091a6  jb      short loc_18000918B
0x1800091a8  mov     ecx, dword ptr [rsp+4F0h+var_490+4]
0x1800091ac  movsxd  rax, dword ptr [rsp+4F0h+var_490+8]
0x1800091b1  inc     r15d
0x1800091b4  add     r10, rax
0x1800091b7  movsxd  rax, r12d
0x1800091ba  add     r11, rax
0x1800091bd  cmp     r15d, ecx
0x1800091c0  jb      short loc_18000917D
0x1800091c2  mov     rdi, [rdi]
0x1800091c5  mov     rcx, [rdi+58h]
0x1800091c9  test    rcx, rcx
0x1800091cc  jz      short loc_1800091ED
0x1800091ce  mov     rax, [rcx]
0x1800091d1  lea     rdx, [rsp+4F0h+var_490]
0x1800091d6  mov     rax, [rax+30h]
0x1800091da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091df  dec     dword ptr [rdi+3Ch]
0x1800091e2  test    eax, eax
0x1800091e4  jns     short loc_1800091ED
0x1800091e6  mov     ecx, eax
0x1800091e8  call    ?MapHRESULTToGpStatus@@YA?AW4Status@@J@Z; MapHRESULTToGpStatus(long)
0x1800091ed  mov     rcx, rsi
0x1800091f0  call    GpFree
0x1800091f5  mov     rdx, r14; hDC
0x1800091f8  xor     ecx, ecx; hWnd
0x1800091fa  call    cs:__imp_ReleaseDC
0x180009200  jmp     loc_180009084
0x180009205  mov     ebx, 3
0x18000920a  jmp     short loc_1800091F5
0x18000920c  mov     rcx, [rdi]
0x18000920f  mov     esi, 1
0x180009214  mov     r15d, 26200Ah
0x18000921a  test    rcx, rcx
0x18000921d  jz      short loc_18000923E
0x18000921f  mov     byte ptr [rsp+4F0h+lpbmi], r13b
0x180009224  xor     r9d, r9d
0x180009227  mov     r8d, esi
0x18000922a  mov     [rsp+4F0h+lpvBits], r13
0x18000922f  mov     edx, r15d
0x180009232  call    ?ConvertFormat@CopyOnWriteBitmap@@AEAA?AW4Status@@HW4DitherType@@W4PaletteType@@PEAUColorPalette@@E@Z; CopyOnWriteBitmap::ConvertFormat(int,DitherType,PaletteType,ColorPalette *,uchar)
0x180009237  mov     ecx, eax
0x180009239  call    ?MapHRESULTToGpStatus@@YA?AW4Status@@J@Z; MapHRESULTToGpStatus(long)
0x18000923e  cmp     [rsp+4F0h+piconinfo.hbmMask], r13
0x180009243  jz      loc_180009094
0x180009249  xor     ecx, ecx; hWnd
0x18000924b  mov     ebx, 7
0x180009250  call    cs:__imp_GetDC
0x180009256  mov     r14, rax
0x180009259  test    rax, rax
0x18000925c  jz      loc_180009084
0x180009262  xor     edx, edx; Val
0x180009264  lea     rcx, [rbp+3F0h+bmi.bmiHeader.biWidth]; void *
0x180009268  mov     r8d, 424h; Size
0x18000926e  call    memset_0
0x180009273  mov     rdx, [rsp+4F0h+piconinfo.hbmMask]; hbm
0x180009278  lea     rax, [rbp+3F0h+bmi]
0x18000927c  mov     [rsp+4F0h+usage], r13d; usage
0x180009281  lea     r12d, [rbx+21h]
0x180009285  mov     [rsp+4F0h+lpbmi], rax; lpbmi
0x18000928a  xor     r9d, r9d; cLines
0x18000928d  xor     r8d, r8d; start
0x180009290  mov     [rsp+4F0h+lpvBits], r13; lpvBits
0x180009295  mov     rcx, r14; hdc
0x180009298  mov     [rbp+3F0h+bmi.bmiHeader.biSize], r12d
0x18000929c  call    cs:__imp_GetDIBits
0x1800092a2  test    eax, eax
0x1800092a4  jz      loc_1800091F5
0x1800092aa  mov     ecx, [rbp+3F0h+bmi.bmiHeader.biHeight]
0x1800092ad  mov     r8d, 0FFFFFFFFh
0x1800092b3  mov     edx, [rbp+3F0h+bmi.bmiHeader.biWidth]
0x1800092b6  neg     ecx
0x1800092b8  mov     [rbp+3F0h+bmi.bmiHeader.biSize], r12d
0x1800092bc  cmovs   ecx, [rbp+3F0h+bmi.bmiHeader.biHeight]
0x1800092c0  neg     ecx
0x1800092c2  shl     rdx, 2
0x1800092c6  mov     [rbp+3F0h+bmi.bmiHeader.biHeight], ecx
0x1800092c9  mov     qword ptr [rbp+3F0h+bmi.bmiHeader.biPlanes], 200001h
0x1800092d1  mov     [rbp+3F0h+bmi.bmiHeader.biSizeImage], r13d
0x1800092d5  mov     qword ptr [rbp+3F0h+bmi.bmiHeader.biClrUsed], r13
0x1800092d9  cmp     rdx, r8
0x1800092dc  ja      short loc_1800092F6
0x1800092de  mov     eax, ecx
0x1800092e0  neg     eax
0x1800092e2  cmovs   eax, ecx
0x1800092e5  mov     ecx, eax
0x1800092e7  mov     eax, edx
0x1800092e9  imul    rcx, rax
0x1800092ed  cmp     rcx, r8
0x1800092f0  jbe     loc_1800090D7
0x1800092f6  mov     ebx, 0Bh
0x1800092fb  jmp     loc_1800091F5
0x180009300  mov     ebx, 2
0x180009305  jmp     loc_1800090A4
```
