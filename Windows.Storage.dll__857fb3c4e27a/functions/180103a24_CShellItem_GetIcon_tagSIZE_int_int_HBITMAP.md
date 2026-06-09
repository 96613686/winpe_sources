# CShellItem::_GetIcon(tagSIZE,int,int,HBITMAP__ * *)

- ea: `0x180103a24`
- end: `0x180103bb3`
- name: `?_GetIcon@CShellItem@@IEAAJUtagSIZE@@HHPEAPEAUHBITMAP__@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(CShellItem *__hidden this, struct tagSIZE, int, int, HBITMAP *)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180284ef0`

## callees

- `0x1800c8fb0`
- `0x180103a24`
- `0x180103cc0`
- `0x180141530`
- `0x180141a90`
- `0x1801420e4`
- `0x1801425ec`
- `0x1802c1110`
- `0x1803a4cb0`
- `0x1804edc88`
- `0x1804edcec`
- `0x1804edd04`
- `0x1804ee550`
- `0x1804ee730`
- `0x1804eeb70`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180645248`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180645248`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180103b40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180103b40`
- `GDI32!DeleteObject` at `0x1806450af`
- `GDI32!DeleteObject` at `0x1806451a9`
- `GDI32!DeleteObject` at `0x1806452cf`
- `GDI32!DeleteObject` at `0x1806450af`
- `GDI32!DeleteObject` at `0x1806451a9`
- `GDI32!DeleteObject` at `0x1806452cf`
- `GDI32!CreateSolidBrush` at `0x180645188`
- `GDI32!CreateSolidBrush` at `0x180645188`
- `GDI32!SelectObject` at `0x1806450c2`
- `GDI32!SelectObject` at `0x180645228`
- `GDI32!SelectObject` at `0x1806452b5`
- `GDI32!SelectObject` at `0x1806452dc`
- `GDI32!SelectObject` at `0x1806450c2`
- `GDI32!SelectObject` at `0x180645228`
- `GDI32!SelectObject` at `0x1806452b5`
- `GDI32!SelectObject` at `0x1806452dc`
- `GDI32!CreateCompatibleDC` at `0x180645098`
- `GDI32!CreateCompatibleDC` at `0x18064520d`
- `GDI32!CreateCompatibleDC` at `0x180645098`
- `GDI32!CreateCompatibleDC` at `0x18064520d`
- `GDI32!GdiAlphaBlend` at `0x1806452a9`
- `GDI32!GdiAlphaBlend` at `0x1806452a9`
- `GDI32!DeleteDC` at `0x1806452be`
- `GDI32!DeleteDC` at `0x1806452e5`
- `GDI32!DeleteDC` at `0x1806452be`
- `GDI32!DeleteDC` at `0x1806452e5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFillRectClr` at `0x180645112`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFillRectClr` at `0x180645112`
- `ext-ms-win-ntuser-gui-l1-1-1!FrameRect` at `0x1806451a0`
- `ext-ms-win-ntuser-gui-l1-1-1!FrameRect` at `0x1806451a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CShellItem::_GetIcon(CShellItem *this, struct tagSIZE a2, int a3, int a4, HBITMAP *a5)
{
  struct IShellItem *v7; // rsi
  int ParentAndChildIDListFromItem; // edi
  int v9; // ecx
  int BitmapFromIcon; // eax
  void *v11; // rcx
  int v13; // r14d
  HDC CompatibleDC; // rax
  HDC v15; // r15
  unsigned int TileBackgroundColorForItem; // eax
  int v17; // r13d
  int v18; // esi
  char v19; // di
  int v20; // ebx
  HBRUSH SolidBrush; // rax
  HBRUSH v22; // rbx
  LONG IconSizeForPhotoMode; // eax
  unsigned int v24; // esi
  HDC v25; // rax
  HDC hdcSrc; // r14
  HGDIOBJ v27; // rbx
  LANGID ThreadUILanguage; // ax
  int v29; // eax
  BLENDFUNCTION v30; // [rsp+60h] [rbp-A0h] BYREF
  int xoriginDest[4]; // [rsp+68h] [rbp-98h] BYREF
  struct tagSIZE wDest; // [rsp+78h] [rbp-88h] BYREF
  HGDIOBJ ho; // [rsp+80h] [rbp-80h] BYREF
  int v34; // [rsp+88h] [rbp-78h]
  HGDIOBJ h; // [rsp+90h] [rbp-70h] BYREF
  struct tagRECT v36; // [rsp+98h] [rbp-68h] BYREF
  HGDIOBJ v37; // [rsp+A8h] [rbp-58h]
  _QWORD v38[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v39; // [rsp+D0h] [rbp-30h]
  int v40; // [rsp+E0h] [rbp-20h]
  struct tagRGBQUAD *v41; // [rsp+E8h] [rbp-18h] BYREF
  int v42; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+F8h] [rbp-8h] BYREF
  struct IShellFolder *v44; // [rsp+100h] [rbp+0h] BYREF
  RECT rc; // [rsp+108h] [rbp+8h] BYREF

  v34 = a4;
  *(struct tagSIZE *)xoriginDest = a2;
  *a5 = 0;
  v44 = 0;
  pv = 0;
  v7 = (struct IShellItem *)(((unsigned __int64)this + 8) & -(__int64)(this != 0));
  ParentAndChildIDListFromItem = GetParentAndChildIDListFromItem(
                                   v7,
                                   &GUID_000214e6_0000_0000_c000_000000000046,
                                   &v44,
                                   &pv);
  if ( ParentAndChildIDListFromItem >= 0 )
  {
    v42 = 0;
    if ( a4 )
    {
      v38[0] = 0;
      v38[1] = v44;
      v38[2] = pv;
      v38[3] = 0;
      v39 = 0;
      v40 = 512;
      ParentAndChildIDListFromItem = SHMapIDListToSystemImageListIndexAsync2(v38, &v42, 0);
      if ( ParentAndChildIDListFromItem < 0 )
        goto LABEL_11;
      v9 = v42;
    }
    else
    {
      v30 = 0;
      _GetILIndexFromItem(v44, (const struct _ITEMID_CHILD *)pv, 0, (int *)&v30);
      v9 = (int)v30;
      v42 = (int)v30;
      if ( *(int *)&v30 < 0 )
      {
        ParentAndChildIDListFromItem = -2147483638;
        goto LABEL_11;
      }
    }
    if ( (a3 & 0x80u) == 0 )
    {
      if ( (a3 & 0x20000000) != 0 )
        BitmapFromIcon = CreateBitmapFromIcon(0, v9, 0, (const struct tagSIZE *)xoriginDest, a5);
      else
        BitmapFromIcon = _CreateBitmapFromSystemImageListWithAlpha(v9, a4, xoriginDest[0], a5);
      ParentAndChildIDListFromItem = BitmapFromIcon;
      goto LABEL_11;
    }
    v13 = a3 & 0x40;
    if ( v13 )
      xoriginDest[1] = GetWideThumbnailHeightFromWidth(xoriginDest[0]);
    ho = 0;
    v41 = 0;
    ParentAndChildIDListFromItem = Create32BitHBITMAP(
                                     0,
                                     (const struct tagSIZE *)xoriginDest,
                                     (void **)&v41,
                                     (HBITMAP *)&ho);
    if ( ParentAndChildIDListFromItem >= 0 )
    {
      CompatibleDC = CreateCompatibleDC(0);
      v15 = CompatibleDC;
      if ( !CompatibleDC )
      {
        ParentAndChildIDListFromItem = -2147467259;
LABEL_20:
        DeleteObject(ho);
        goto LABEL_11;
      }
      v37 = SelectObject(CompatibleDC, ho);
      TileBackgroundColorForItem = GetTileBackgroundColorForItem(v7);
      *(_QWORD *)&rc.left = 0;
      v17 = xoriginDest[0];
      rc.right = xoriginDest[0];
      rc.bottom = xoriginDest[1];
      v18 = (unsigned __int8)TileBackgroundColorForItem;
      v19 = BYTE2(TileBackgroundColorForItem);
      v20 = BYTE1(TileBackgroundColorForItem);
      SHFillRectClr(
        v15,
        &rc,
        (unsigned __int8)TileBackgroundColorForItem
      | (BYTE2(TileBackgroundColorForItem) << 16)
      | (unsigned int)(v20 << 8));
      SolidBrush = CreateSolidBrush(
                     (unsigned __int8)(228 * v18 / 255 + 27)
                   | ((unsigned __int8)(28 * v20 + 27) << 8)
                   | ((unsigned __int8)(28 * v19 + 27) << 16));
      v22 = SolidBrush;
      if ( SolidBrush )
      {
        FrameRect(v15, &rc, SolidBrush);
        DeleteObject(v22);
      }
      DIBSectionUtil::MakeOpaque(v17, xoriginDest[1], v41);
      h = 0;
      if ( v13 )
        IconSizeForPhotoMode = GetIconSizeForPhotoMode(v17);
      else
        IconSizeForPhotoMode = GetIconSizeForTileMode(v17);
      v24 = IconSizeForPhotoMode;
      wDest.cx = IconSizeForPhotoMode;
      wDest.cy = IconSizeForPhotoMode;
      ParentAndChildIDListFromItem = CreateBitmapFromIcon(0, v42, v34, &wDest, (HBITMAP *)&h);
      if ( ParentAndChildIDListFromItem >= 0 )
      {
        v25 = CreateCompatibleDC(0);
        hdcSrc = v25;
        if ( v25 )
        {
          ParentAndChildIDListFromItem = 0;
          v27 = SelectObject(v25, h);
          *(_QWORD *)&v36.left = 0;
          v36.right = v17;
          v36.bottom = xoriginDest[1];
          *(_OWORD *)xoriginDest = 0;
          ThreadUILanguage = GetThreadUILanguage();
          v29 = IsBiDiLocale(ThreadUILanguage);
          GetIconRectFromBackgroundRect(v24, v29, &v36, (struct tagRECT *)xoriginDest);
          v30 = (BLENDFUNCTION)33488896;
          GdiAlphaBlend(
            v15,
            xoriginDest[0],
            xoriginDest[1],
            wDest.cx,
            wDest.cy,
            hdcSrc,
            0,
            0,
            wDest.cx,
            wDest.cy,
            (BLENDFUNCTION)33488896);
          SelectObject(hdcSrc, v27);
          DeleteDC(hdcSrc);
        }
        else
        {
          ParentAndChildIDListFromItem = -2147467259;
        }
        DeleteObject(h);
      }
      SelectObject(v15, v37);
      DeleteDC(v15);
      if ( ParentAndChildIDListFromItem < 0 )
        goto LABEL_20;
      *a5 = (HBITMAP)ho;
    }
  }
LABEL_11:
  v11 = pv;
  pv = 0;
  CoTaskMemFree(v11);
  if ( v44 )
    ((void (__fastcall *)(struct IShellFolder *))v44->lpVtbl->Release)(v44);
  return (unsigned int)ParentAndChildIDListFromItem;
}

```

## disassembly

```asm
0x180103a24  mov     [rsp-8+arg_10], rbx
0x180103a29  push    rbp
0x180103a2a  push    rsi
0x180103a2b  push    rdi
0x180103a2c  push    r12
0x180103a2e  push    r13
0x180103a30  push    r14
0x180103a32  push    r15
0x180103a34  lea     rbp, [rsp-20h]
0x180103a39  sub     rsp, 120h
0x180103a40  mov     rax, cs:__security_cookie
0x180103a47  xor     rax, rsp
0x180103a4a  mov     [rbp+50h+var_38], rax
0x180103a4e  mov     ebx, r9d
0x180103a51  mov     [rbp+50h+var_C8], ebx
0x180103a54  mov     r14d, r8d
0x180103a57  mov     qword ptr [rsp+150h+xoriginDest], rdx
0x180103a5c  mov     r12, [rbp+50h+arg_20]
0x180103a63  xor     r13d, r13d
0x180103a66  mov     [r12], r13
0x180103a6a  mov     [rbp+50h+var_50], r13
0x180103a6e  mov     [rbp+50h+pv], r13
0x180103a72  lea     rax, [rcx+8]
0x180103a76  neg     rcx
0x180103a79  sbb     rsi, rsi
0x180103a7c  and     rsi, rax
0x180103a7f  lea     r9, [rbp+50h+pv]
0x180103a83  lea     r8, [rbp+50h+var_50]
0x180103a87  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x180103a8e  mov     rcx, rsi
0x180103a91  call    GetParentAndChildIDListFromItem
0x180103a96  mov     edi, eax
0x180103a98  test    eax, eax
0x180103a9a  js      loc_180103B38
0x180103aa0  mov     [rbp+50h+var_60], r13d
0x180103aa4  test    ebx, ebx
0x180103aa6  jnz     short loc_180103AD4
0x180103aa8  mov     dword ptr [rsp+150h+var_F0.BlendOp], r13d
0x180103aad  lea     r9, [rsp+150h+var_F0]; int *
0x180103ab2  xor     r8d, r8d; unsigned int
0x180103ab5  mov     rdx, [rbp+50h+pv]; struct _ITEMID_CHILD *
0x180103ab9  mov     rcx, [rbp+50h+var_50]; struct IShellFolder *
0x180103abd  call    ?_GetILIndexFromItem@@YAJPEAUIShellFolder@@PEFBU_ITEMID_CHILD@@IPEAH@Z; _GetILIndexFromItem(IShellFolder *,_ITEMID_CHILD const *,uint,int *)
0x180103ac2  mov     ecx, dword ptr [rsp+150h+var_F0.BlendOp]
0x180103ac6  mov     [rbp+50h+var_60], ecx
0x180103ac9  test    ecx, ecx
0x180103acb  jns     short loc_180103B14
0x180103acd  mov     edi, 8000000Ah
0x180103ad2  jmp     short loc_180103B38
0x180103ad4  mov     [rbp+50h+var_A0], r13
0x180103ad8  mov     rax, [rbp+50h+var_50]
0x180103adc  mov     [rbp+50h+var_98], rax
0x180103ae0  mov     rax, [rbp+50h+pv]
0x180103ae4  mov     [rbp+50h+var_90], rax
0x180103ae8  mov     [rbp+50h+var_88], r13
0x180103aec  xorps   xmm0, xmm0
0x180103aef  movdqu  [rbp+50h+var_80], xmm0
0x180103af4  mov     [rbp+50h+var_70], 200h
0x180103afb  xor     r8d, r8d
0x180103afe  lea     rdx, [rbp+50h+var_60]
0x180103b02  lea     rcx, [rbp+50h+var_A0]
0x180103b06  call    SHMapIDListToSystemImageListIndexAsync2
0x180103b0b  mov     edi, eax
0x180103b0d  test    eax, eax
0x180103b0f  js      short loc_180103B38
0x180103b11  mov     ecx, [rbp+50h+var_60]; int
0x180103b14  test    r14b, r14b
0x180103b17  js      short loc_180103B97
0x180103b19  bt      r14d, 1Dh
0x180103b1e  jnb     short loc_180103B86
0x180103b20  mov     qword ptr [rsp+150h+hDest], r12; HBITMAP *
0x180103b25  lea     r9, [rsp+150h+xoriginDest]; struct tagSIZE *
0x180103b2a  xor     r8d, r8d; int
0x180103b2d  mov     edx, ecx; int
0x180103b2f  xor     ecx, ecx; hicon
0x180103b31  call    ?CreateBitmapFromIcon@@YAJPEAUHICON__@@HHPEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z; CreateBitmapFromIcon(HICON__ *,int,int,tagSIZE const *,HBITMAP__ * *)
0x180103b36  mov     edi, eax
0x180103b38  mov     rcx, [rbp+50h+pv]; pv
0x180103b3c  mov     [rbp+50h+pv], r13
0x180103b40  call    cs:__imp_CoTaskMemFree
0x180103b46  nop
0x180103b47  mov     rcx, [rbp+50h+var_50]
0x180103b4b  test    rcx, rcx
0x180103b4e  jz      short loc_180103B5D
0x180103b50  mov     rax, [rcx]
0x180103b53  mov     rax, [rax+10h]
0x180103b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103b5c  nop
0x180103b5d  mov     eax, edi
0x180103b5f  mov     rcx, [rbp+50h+var_38]
0x180103b63  xor     rcx, rsp; StackCookie
0x180103b66  call    __security_check_cookie
0x180103b6b  mov     rbx, [rsp+150h+arg_10]
0x180103b73  add     rsp, 120h
0x180103b7a  pop     r15
0x180103b7c  pop     r14
0x180103b7e  pop     r13
0x180103b80  pop     r12
0x180103b82  pop     rdi
0x180103b83  pop     rsi
0x180103b84  pop     rbp
0x180103b85  retn
0x180103b86  mov     r9, r12; HBITMAP *
0x180103b89  mov     r8d, [rsp+150h+xoriginDest]; int
0x180103b8e  mov     edx, ebx; int
0x180103b90  call    ?_CreateBitmapFromSystemImageListWithAlpha@@YAJHHHPEAPEAUHBITMAP__@@@Z; _CreateBitmapFromSystemImageListWithAlpha(int,int,int,HBITMAP__ * *)
0x180103b95  jmp     short loc_180103B36
0x180103b97  and     r14d, 40h
0x180103b9b  jz      loc_180645070
0x180103ba1  mov     ecx, [rsp+150h+xoriginDest]; unsigned int
0x180103ba5  call    ?GetWideThumbnailHeightFromWidth@@YAII@Z; GetWideThumbnailHeightFromWidth(uint)
0x180103baa  mov     [rsp+150h+xoriginDest+4], eax
0x180103bae  jmp     loc_180645070
0x180645070  mov     [rbp+50h+ho], r13
0x180645074  mov     [rbp+50h+var_68], r13
0x180645078  lea     r9, [rbp+50h+ho]; HBITMAP *
0x18064507c  lea     r8, [rbp+50h+var_68]; void **
0x180645080  lea     rdx, [rsp+150h+xoriginDest]; struct tagSIZE *
0x180645085  xor     ecx, ecx; HDC
0x180645087  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x18064508c  mov     edi, eax
0x18064508e  test    eax, eax
0x180645090  js      loc_180103B38
0x180645096  xor     ecx, ecx; hdc
0x180645098  call    cs:__imp_CreateCompatibleDC
0x18064509e  mov     r15, rax
0x1806450a1  test    rax, rax
0x1806450a4  jnz     short loc_1806450BB
0x1806450a6  mov     edi, 80004005h
0x1806450ab  mov     rcx, [rbp+50h+ho]; ho
0x1806450af  call    cs:__imp_DeleteObject
0x1806450b5  nop
0x1806450b6  jmp     loc_180103B38
0x1806450bb  mov     rdx, [rbp+50h+ho]; h
0x1806450bf  mov     rcx, r15; hdc
0x1806450c2  call    cs:__imp_SelectObject
0x1806450c8  mov     [rbp+50h+var_A8], rax
0x1806450cc  mov     rcx, rsi; struct IShellItem *
0x1806450cf  call    ?GetTileBackgroundColorForItem@@YAKPEAUIShellItem@@@Z; GetTileBackgroundColorForItem(IShellItem *)
0x1806450d4  mov     qword ptr [rbp+50h+rc.left], r13
0x1806450d8  mov     r13d, [rsp+150h+xoriginDest]
0x1806450dd  mov     [rbp+50h+rc.right], r13d
0x1806450e1  mov     ecx, [rsp+150h+xoriginDest+4]
0x1806450e5  mov     [rbp+50h+rc.bottom], ecx
0x1806450e8  movzx   esi, al
0x1806450eb  mov     ecx, eax
0x1806450ed  shr     ecx, 10h
0x1806450f0  movzx   edi, cl
0x1806450f3  movzx   ebx, ax
0x1806450f6  shr     ebx, 8
0x1806450f9  mov     r8d, ebx
0x1806450fc  shl     r8d, 8
0x180645100  mov     eax, edi
0x180645102  shl     eax, 10h
0x180645105  or      r8d, eax
0x180645108  or      r8d, esi
0x18064510b  lea     rdx, [rbp+50h+rc]
0x18064510f  mov     rcx, r15
0x180645112  call    cs:__imp_SHFillRectClr
0x180645118  imul    ecx, ebx, 0E4h
0x18064511e  mov     r11d, 80808081h
0x180645124  mov     eax, r11d
0x180645127  imul    ecx
0x180645129  add     edx, ecx
0x18064512b  sar     edx, 7
0x18064512e  mov     eax, edx
0x180645130  shr     eax, 1Fh
0x180645133  add     edx, eax
0x180645135  mov     r10b, 1Bh
0x180645138  add     dl, r10b
0x18064513b  movzx   r9d, dl
0x18064513f  shl     r9d, 8
0x180645143  imul    ecx, edi, 0E4h
0x180645149  mov     eax, r11d
0x18064514c  imul    ecx
0x18064514e  add     edx, ecx
0x180645150  sar     edx, 7
0x180645153  mov     ecx, edx
0x180645155  shr     ecx, 1Fh
0x180645158  add     edx, ecx
0x18064515a  add     dl, r10b
0x18064515d  movzx   ecx, dl
0x180645160  shl     ecx, 10h
0x180645163  or      ecx, r9d
0x180645166  imul    r8d, esi, 0E4h
0x18064516d  mov     eax, r11d
0x180645170  imul    r8d
0x180645173  add     edx, r8d
0x180645176  sar     edx, 7
0x180645179  mov     eax, edx
0x18064517b  shr     eax, 1Fh
0x18064517e  add     edx, eax
0x180645180  add     dl, r10b
0x180645183  movzx   eax, dl
0x180645186  or      ecx, eax; color
0x180645188  call    cs:__imp_CreateSolidBrush
0x18064518e  mov     rbx, rax
0x180645191  test    rax, rax
0x180645194  jz      short loc_1806451AF
0x180645196  mov     r8, rax; hbr
0x180645199  lea     rdx, [rbp+50h+rc]; lprc
0x18064519d  mov     rcx, r15; hDC
0x1806451a0  call    cs:__imp_FrameRect
0x1806451a6  mov     rcx, rbx; ho
0x1806451a9  call    cs:__imp_DeleteObject
0x1806451af  mov     r8, [rbp+50h+var_68]; struct tagRGBQUAD *
0x1806451b3  mov     edx, [rsp+150h+xoriginDest+4]; unsigned int
0x1806451b7  mov     ecx, r13d; unsigned int
0x1806451ba  call    ?MakeOpaque@DIBSectionUtil@@SAXIIPEAUtagRGBQUAD@@@Z; DIBSectionUtil::MakeOpaque(uint,uint,tagRGBQUAD *)
0x1806451bf  mov     [rbp+50h+h], 0
0x1806451c7  mov     ecx, r13d; unsigned int
0x1806451ca  test    r14d, r14d
0x1806451cd  jz      short loc_1806451D6
0x1806451cf  call    ?GetIconSizeForPhotoMode@@YAII@Z; GetIconSizeForPhotoMode(uint)
0x1806451d4  jmp     short loc_1806451DB
0x1806451d6  call    ?GetIconSizeForTileMode@@YAII@Z; GetIconSizeForTileMode(uint)
0x1806451db  mov     esi, eax
0x1806451dd  mov     [rsp+150h+wDest], eax
0x1806451e1  mov     [rsp+150h+var_D4], eax
0x1806451e5  lea     rax, [rbp+50h+h]
0x1806451e9  mov     qword ptr [rsp+150h+hDest], rax; HBITMAP *
0x1806451ee  lea     r9, [rsp+150h+wDest]; struct tagSIZE *
0x1806451f3  mov     r8d, [rbp+50h+var_C8]; int
0x1806451f7  mov     edx, [rbp+50h+var_60]; int
0x1806451fa  xor     ecx, ecx; hicon
0x1806451fc  call    ?CreateBitmapFromIcon@@YAJPEAUHICON__@@HHPEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z; CreateBitmapFromIcon(HICON__ *,int,int,tagSIZE const *,HBITMAP__ * *)
0x180645201  mov     edi, eax
0x180645203  test    eax, eax
0x180645205  js      loc_1806452D5
0x18064520b  xor     ecx, ecx; hdc
0x18064520d  call    cs:__imp_CreateCompatibleDC
0x180645213  mov     r14, rax
0x180645216  test    rax, rax
0x180645219  jz      loc_1806452C6
0x18064521f  xor     edi, edi
0x180645221  mov     rdx, [rbp+50h+h]; h
0x180645225  mov     rcx, rax; hdc
0x180645228  call    cs:__imp_SelectObject
0x18064522e  mov     rbx, rax
0x180645231  mov     qword ptr [rbp+50h+var_B8.left], rdi
0x180645235  mov     [rbp+50h+var_B8.right], r13d
0x180645239  mov     eax, [rsp+150h+xoriginDest+4]
0x18064523d  mov     [rbp+50h+var_B8.bottom], eax
0x180645240  xorps   xmm0, xmm0
0x180645243  movups  xmmword ptr [rsp+150h+xoriginDest], xmm0
0x180645248  call    cs:__imp_GetThreadUILanguage
0x18064524e  movzx   ecx, ax; unsigned int
0x180645251  call    ?IsBiDiLocale@@YAHK@Z; IsBiDiLocale(ulong)
0x180645256  lea     r9, [rsp+150h+xoriginDest]; struct tagRECT *
0x18064525b  lea     r8, [rbp+50h+var_B8]; struct tagRECT *
0x18064525f  mov     edx, eax; int
0x180645261  mov     ecx, esi; unsigned int
0x180645263  call    ?GetIconRectFromBackgroundRect@@YAXIHPEBUtagRECT@@PEAU1@@Z; GetIconRectFromBackgroundRect(uint,int,tagRECT const *,tagRECT *)
0x180645268  xor     ecx, ecx
0x18064526a  mov     dword ptr [rsp+150h+var_F0.BlendOp], 1FF0000h
0x180645272  mov     eax, dword ptr [rsp+150h+var_F0.BlendOp]
0x180645276  mov     dword ptr [rsp+150h+ftn.BlendOp], eax; ftn
0x18064527a  mov     eax, [rsp+150h+var_D4]
0x18064527e  mov     [rsp+150h+hSrc], eax; hSrc
0x180645282  mov     r9d, [rsp+150h+wDest]; wDest
0x180645287  mov     [rsp+150h+wSrc], r9d; wSrc
0x18064528c  mov     [rsp+150h+yoriginSrc], ecx; yoriginSrc
0x180645290  mov     [rsp+150h+xoriginSrc], ecx; xoriginSrc
0x180645294  mov     [rsp+150h+hdcSrc], r14; hdcSrc
0x180645299  mov     [rsp+150h+hDest], eax; hDest
0x18064529d  mov     r8d, [rsp+150h+xoriginDest+4]; yoriginDest
0x1806452a2  mov     edx, [rsp+150h+xoriginDest]; xoriginDest
0x1806452a6  mov     rcx, r15; hdcDest
0x1806452a9  call    cs:__imp_GdiAlphaBlend
0x1806452af  mov     rdx, rbx; h
0x1806452b2  mov     rcx, r14; hdc
0x1806452b5  call    cs:__imp_SelectObject
0x1806452bb  mov     rcx, r14; hdc
0x1806452be  call    cs:__imp_DeleteDC
0x1806452c4  jmp     short loc_1806452CB
0x1806452c6  mov     edi, 80004005h
0x1806452cb  mov     rcx, [rbp+50h+h]; ho
0x1806452cf  call    cs:__imp_DeleteObject
0x1806452d5  mov     rdx, [rbp+50h+var_A8]; h
0x1806452d9  mov     rcx, r15; hdc
0x1806452dc  call    cs:__imp_SelectObject
0x1806452e2  mov     rcx, r15; hdc
0x1806452e5  call    cs:__imp_DeleteDC
0x1806452eb  xor     r13d, r13d
0x1806452ee  test    edi, edi
0x1806452f0  js      loc_1806450AB
0x1806452f6  mov     rax, [rbp+50h+ho]
0x1806452fa  mov     [r12], rax
0x1806452fe  jmp     loc_180103B38
```
