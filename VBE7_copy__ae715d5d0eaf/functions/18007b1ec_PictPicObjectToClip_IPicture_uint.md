# PictPicObjectToClip(IPicture *,uint)

- ea: `0x18007b1ec`
- end: `0x18007b4ce`
- name: `?PictPicObjectToClip@@YAJPEAUIPicture@@I@Z`
- size: `738`
- prototype: `__int64 __fastcall(struct IPicture *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18007c210`

## callees

- `0x18005c860`
- `0x18007af18`
- `0x18007af50`
- `0x18007b1ec`
- `0x18007b834`
- `0x18007b924`
- `0x18007bd0c`
- `0x18007c48c`
- `0x18007c4e0`
- `0x180379380`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18007b32a`
- `KERNEL32!GlobalAlloc` at `0x18007b32a`
- `KERNEL32!GlobalLock` at `0x18007b36e`
- `KERNEL32!GlobalLock` at `0x18007b36e`
- `KERNEL32!GlobalUnlock` at `0x18007b3b3`
- `KERNEL32!GlobalUnlock` at `0x18007b3b3`
- `KERNEL32!GlobalFree` at `0x18007b363`
- `KERNEL32!GlobalFree` at `0x18007b363`
- `USER32!SetClipboardData` at `0x18007b472`
- `USER32!SetClipboardData` at `0x18007b48f`
- `USER32!SetClipboardData` at `0x18007b472`
- `USER32!SetClipboardData` at `0x18007b48f`
- `USER32!CloseClipboard` at `0x18007b4a2`
- `USER32!CloseClipboard` at `0x18007b4a2`
- `USER32!OpenClipboard` at `0x18007b296`
- `USER32!OpenClipboard` at `0x18007b296`
- `GDI32!CopyMetaFileA` at `0x18007b350`
- `GDI32!CopyMetaFileA` at `0x18007b350`
- `GDI32!CopyEnhMetaFileA` at `0x18007b2f5`
- `GDI32!CopyEnhMetaFileA` at `0x18007b2f5`

## pseudocode

```c
__int64 __fastcall PictPicObjectToClip(struct IPicture *a1, UINT a2)
{
  struct IPicture *v3; // rsi
  int v4; // r14d
  int v5; // ebx
  __int16 v6; // bx
  HWND ThreadHwndMain; // rax
  void *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  HPALETTE v11; // rax
  HGLOBAL hMem; // [rsp+20h] [rbp-20h] BYREF
  HANDLE v14; // [rsp+28h] [rbp-18h] BYREF
  HMETAFILE v15[2]; // [rsp+30h] [rbp-10h] BYREF
  HENHMETAFILE hEnh; // [rsp+80h] [rbp+40h] BYREF
  HBITMAP v17; // [rsp+88h] [rbp+48h] BYREF

  v3 = a1;
  hMem = 0;
  v14 = 0;
  v4 = 0;
  if ( (unsigned int)_FIsShadowBitmap(a1) )
  {
    v3 = _LppictureCopyShadowBitmap(v3);
    if ( !v3 )
    {
LABEL_3:
      v5 = -2147024882;
      goto LABEL_48;
    }
    v4 = 1;
  }
  v6 = PicType(v3);
  if ( !v6 )
  {
    if ( a2 && a2 != 2 && a2 != 8 && a2 != 9 && a2 != 14 && a2 != 3 )
      goto LABEL_35;
LABEL_47:
    v5 = 0;
    goto LABEL_48;
  }
  ThreadHwndMain = GetThreadHwndMain();
  if ( !OpenClipboard(ThreadHwndMain) )
  {
    v5 = -2146827767;
    goto LABEL_48;
  }
  if ( v6 != 1 )
  {
    if ( v6 != 2 )
    {
      if ( v6 != 4 )
      {
        v5 = -2146827828;
        goto LABEL_48;
      }
      if ( !a2 || a2 == 3 || a2 == 14 )
      {
        a2 = 14;
        ((void (__fastcall *)(struct IPicture *, HENHMETAFILE *))v3->lpVtbl->get_Handle)(v3, &hEnh);
        v8 = CopyEnhMetaFileA(hEnh, 0);
        if ( !v8 )
          goto LABEL_3;
        hMem = v8;
LABEL_43:
        if ( !v8 )
          goto LABEL_45;
        goto LABEL_44;
      }
LABEL_35:
      v5 = -2146827827;
      goto LABEL_48;
    }
    if ( a2 && a2 != 3 && a2 != 14 )
      goto LABEL_35;
    a2 = 3;
    hMem = GlobalAlloc(0x42u, 0x18u);
    if ( !hMem )
      goto LABEL_3;
    ((void (__fastcall *)(struct IPicture *, HMETAFILE *))v3->lpVtbl->get_Handle)(v3, v15);
    v15[0] = CopyMetaFileA(v15[0], 0);
    if ( !v15[0] )
    {
      GlobalFree(hMem);
      goto LABEL_3;
    }
    v9 = GlobalLock(hMem);
    v9[2] = v15[0];
    *(_DWORD *)v9 = 8;
    v10 = v9;
    ((void (__fastcall *)(struct IPicture *, HENHMETAFILE *))v3->lpVtbl->get_Width)(v3, &hEnh);
    ((void (__fastcall *)(struct IPicture *, HBITMAP *))v3->lpVtbl->get_Height)(v3, &v17);
    *((_DWORD *)v10 + 1) = (_DWORD)hEnh;
    *((_DWORD *)v10 + 2) = (_DWORD)v17;
    GlobalUnlock(hMem);
LABEL_42:
    v8 = hMem;
    goto LABEL_43;
  }
  if ( !a2 )
  {
    a2 = 2;
LABEL_41:
    ((void (__fastcall *)(struct IPicture *, HGLOBAL *))v3->lpVtbl->get_Handle)(v3, &hMem);
    ((void (__fastcall *)(struct IPicture *, HANDLE *))v3->lpVtbl->get_hPal)(v3, &v14);
    v5 = _PictCopyBitmapAndPalette((HBITMAP *)&hMem, (HPALETTE *)&v14);
    if ( v5 < 0 )
      goto LABEL_48;
    goto LABEL_42;
  }
  if ( a2 == 2 )
    goto LABEL_41;
  if ( a2 != 8 )
  {
    if ( a2 != 9 )
      goto LABEL_35;
    if ( Sys_ScrSizePalette )
    {
      v11 = PictHpalOfPic(v3);
      v14 = PictCopyPalette(v11);
    }
    goto LABEL_42;
  }
  ((void (__fastcall *)(struct IPicture *, HBITMAP *))v3->lpVtbl->get_Handle)(v3, &v17);
  ((void (__fastcall *)(struct IPicture *, HENHMETAFILE *))v3->lpVtbl->get_hPal)(v3, &hEnh);
  v8 = _PictDibFromBitmap(v17, (HPALETTE)hEnh);
  hMem = v8;
  if ( !v8 )
    goto LABEL_3;
LABEL_44:
  if ( !SetClipboardData(a2, v8) )
    goto LABEL_3;
LABEL_45:
  if ( !v14 )
    goto LABEL_47;
  v5 = -2147024882;
  if ( SetClipboardData(9u, v14) )
    goto LABEL_47;
LABEL_48:
  CloseClipboard();
  if ( v4 && v3 )
    ((void (__fastcall *)(struct IPicture *))v3->lpVtbl->Release)(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007b1ec  mov     [rsp-28h+arg_0], rbx
0x18007b1f1  push    rbp
0x18007b1f2  push    rsi
0x18007b1f3  push    rdi
0x18007b1f4  push    r14
0x18007b1f6  push    r15
0x18007b1f8  mov     rbp, rsp
0x18007b1fb  mov     eax, 40h
0x18007b200  call    _alloca_probe
0x18007b205  sub     rsp, rax
0x18007b208  xor     r15d, r15d
0x18007b20b  mov     edi, edx
0x18007b20d  mov     rsi, rcx
0x18007b210  mov     [rbp+hMem], r15
0x18007b214  mov     [rbp+var_18], r15
0x18007b218  mov     r14d, r15d
0x18007b21b  call    ?_FIsShadowBitmap@@YAHPEAUIPicture@@@Z; _FIsShadowBitmap(IPicture *)
0x18007b220  test    eax, eax
0x18007b222  jz      short loc_18007B244
0x18007b224  mov     rcx, rsi; struct IPicture *
0x18007b227  call    ?_LppictureCopyShadowBitmap@@YAPEAUIPicture@@PEAU1@@Z; _LppictureCopyShadowBitmap(IPicture *)
0x18007b22c  mov     rsi, rax
0x18007b22f  test    rax, rax
0x18007b232  jnz     short loc_18007B23E
0x18007b234  mov     ebx, 8007000Eh
0x18007b239  jmp     loc_18007B4A2
0x18007b23e  mov     r14d, 1
0x18007b244  mov     rcx, rsi; struct IPicture *
0x18007b247  call    ?PicType@@YAFPEAUIPicture@@@Z; PicType(IPicture *)
0x18007b24c  movzx   ebx, ax
0x18007b24f  test    ax, ax
0x18007b252  jnz     short loc_18007B28E
0x18007b254  test    edi, edi
0x18007b256  jz      loc_18007B49F
0x18007b25c  cmp     edi, 2
0x18007b25f  jz      loc_18007B49F
0x18007b265  cmp     edi, 8
0x18007b268  jz      loc_18007B49F
0x18007b26e  cmp     edi, 9
0x18007b271  jz      loc_18007B49F
0x18007b277  cmp     edi, 0Eh
0x18007b27a  jz      loc_18007B49F
0x18007b280  cmp     edi, 3
0x18007b283  jz      loc_18007B49F
0x18007b289  jmp     loc_18007B3D2
0x18007b28e  call    ?GetThreadHwndMain@@YAPEAUHWND__@@XZ; GetThreadHwndMain(void)
0x18007b293  mov     rcx, rax; hWndNewOwner
0x18007b296  call    cs:__imp_OpenClipboard
0x18007b29c  test    eax, eax
0x18007b29e  jnz     short loc_18007B2AA
0x18007b2a0  mov     ebx, 800A0209h
0x18007b2a5  jmp     loc_18007B4A2
0x18007b2aa  movsx   ecx, bx
0x18007b2ad  dec     ecx
0x18007b2af  jz      loc_18007B3BE
0x18007b2b5  dec     ecx
0x18007b2b7  jz      short loc_18007B30D
0x18007b2b9  dec     ecx
0x18007b2bb  jz      short loc_18007B2C1
0x18007b2bd  dec     ecx
0x18007b2bf  jz      short loc_18007B2CB
0x18007b2c1  mov     ebx, 800A01CCh
0x18007b2c6  jmp     loc_18007B4A2
0x18007b2cb  test    edi, edi
0x18007b2cd  jz      short loc_18007B2DD
0x18007b2cf  cmp     edi, 3
0x18007b2d2  jz      short loc_18007B2DD
0x18007b2d4  cmp     edi, 0Eh
0x18007b2d7  jnz     loc_18007B3D2
0x18007b2dd  mov     rax, [rsi]
0x18007b2e0  lea     rdx, [rbp+hEnh]
0x18007b2e4  mov     rcx, rsi
0x18007b2e7  mov     edi, 0Eh
0x18007b2ec  call    qword ptr [rax+18h]
0x18007b2ef  mov     rcx, [rbp+hEnh]; hEnh
0x18007b2f3  xor     edx, edx; lpFileName
0x18007b2f5  call    cs:__imp_CopyEnhMetaFileA
0x18007b2fb  test    rax, rax
0x18007b2fe  jz      loc_18007B234
0x18007b304  mov     [rbp+hMem], rax
0x18007b308  jmp     loc_18007B468
0x18007b30d  test    edi, edi
0x18007b30f  jz      short loc_18007B31F
0x18007b311  cmp     edi, 3
0x18007b314  jz      short loc_18007B31F
0x18007b316  cmp     edi, 0Eh
0x18007b319  jnz     loc_18007B3D2
0x18007b31f  mov     edi, 3
0x18007b324  lea     edx, [rdi+15h]; dwBytes
0x18007b327  lea     ecx, [rdi+3Fh]; uFlags
0x18007b32a  call    cs:__imp_GlobalAlloc
0x18007b330  mov     [rbp+hMem], rax
0x18007b334  test    rax, rax
0x18007b337  jz      loc_18007B234
0x18007b33d  mov     rax, [rsi]
0x18007b340  lea     rdx, [rbp+var_10]
0x18007b344  mov     rcx, rsi
0x18007b347  call    qword ptr [rax+18h]
0x18007b34a  mov     rcx, [rbp+var_10]; HMETAFILE
0x18007b34e  xor     edx, edx; LPCSTR
0x18007b350  call    cs:__imp_CopyMetaFileA
0x18007b356  mov     rcx, [rbp+hMem]; hMem
0x18007b35a  mov     [rbp+var_10], rax
0x18007b35e  test    rax, rax
0x18007b361  jnz     short loc_18007B36E
0x18007b363  call    cs:__imp_GlobalFree
0x18007b369  jmp     loc_18007B234
0x18007b36e  call    cs:__imp_GlobalLock
0x18007b374  mov     rcx, [rbp+var_10]
0x18007b378  lea     rdx, [rbp+hEnh]
0x18007b37c  mov     [rax+10h], rcx
0x18007b380  mov     dword ptr [rax], 8
0x18007b386  mov     r8, [rsi]
0x18007b389  mov     rcx, rsi
0x18007b38c  mov     rbx, rax
0x18007b38f  call    qword ptr [r8+30h]
0x18007b393  mov     r11, [rsi]
0x18007b396  lea     rdx, [rbp+arg_18]
0x18007b39a  mov     rcx, rsi
0x18007b39d  call    qword ptr [r11+38h]
0x18007b3a1  mov     r11d, dword ptr [rbp+hEnh]
0x18007b3a5  mov     [rbx+4], r11d
0x18007b3a9  mov     eax, dword ptr [rbp+arg_18]
0x18007b3ac  mov     [rbx+8], eax
0x18007b3af  mov     rcx, [rbp+hMem]; hMem
0x18007b3b3  call    cs:__imp_GlobalUnlock
0x18007b3b9  jmp     loc_18007B464
0x18007b3be  mov     eax, edi
0x18007b3c0  test    edi, edi
0x18007b3c2  jz      short loc_18007B431
0x18007b3c4  sub     eax, 2
0x18007b3c7  jz      short loc_18007B436
0x18007b3c9  sub     eax, 6
0x18007b3cc  jz      short loc_18007B3FB
0x18007b3ce  dec     eax
0x18007b3d0  jz      short loc_18007B3DC
0x18007b3d2  mov     ebx, 800A01CDh
0x18007b3d7  jmp     loc_18007B4A2
0x18007b3dc  cmp     cs:?Sys_ScrSizePalette@@3IA, r15d; uint Sys_ScrSizePalette
0x18007b3e3  jz      short loc_18007B464
0x18007b3e5  mov     rcx, rsi; struct IPicture *
0x18007b3e8  call    ?PictHpalOfPic@@YAPEAUHPALETTE__@@PEAUIPicture@@@Z; PictHpalOfPic(IPicture *)
0x18007b3ed  mov     rcx, rax; HPALETTE
0x18007b3f0  call    ?PictCopyPalette@@YAPEAUHPALETTE__@@PEAU1@@Z; PictCopyPalette(HPALETTE__ *)
0x18007b3f5  mov     [rbp+var_18], rax
0x18007b3f9  jmp     short loc_18007B464
0x18007b3fb  mov     rax, [rsi]
0x18007b3fe  lea     rdx, [rbp+arg_18]
0x18007b402  mov     rcx, rsi
0x18007b405  call    qword ptr [rax+18h]
0x18007b408  mov     r11, [rsi]
0x18007b40b  lea     rdx, [rbp+hEnh]
0x18007b40f  mov     rcx, rsi
0x18007b412  call    qword ptr [r11+20h]
0x18007b416  mov     rdx, [rbp+hEnh]; HPALETTE
0x18007b41a  mov     rcx, [rbp+arg_18]; HBITMAP
0x18007b41e  call    ?_PictDibFromBitmap@@YAPEAXPEAUHBITMAP__@@PEAUHPALETTE__@@@Z; _PictDibFromBitmap(HBITMAP__ *,HPALETTE__ *)
0x18007b423  mov     [rbp+hMem], rax
0x18007b427  test    rax, rax
0x18007b42a  jnz     short loc_18007B46D
0x18007b42c  jmp     loc_18007B234
0x18007b431  mov     edi, 2
0x18007b436  mov     rax, [rsi]
0x18007b439  lea     rdx, [rbp+hMem]
0x18007b43d  mov     rcx, rsi
0x18007b440  call    qword ptr [rax+18h]
0x18007b443  mov     r11, [rsi]
0x18007b446  lea     rdx, [rbp+var_18]
0x18007b44a  mov     rcx, rsi
0x18007b44d  call    qword ptr [r11+20h]
0x18007b451  lea     rdx, [rbp+var_18]; HPALETTE *
0x18007b455  lea     rcx, [rbp+hMem]; HBITMAP *
0x18007b459  call    ?_PictCopyBitmapAndPalette@@YAJPEAPEAUHBITMAP__@@PEAPEAUHPALETTE__@@@Z; _PictCopyBitmapAndPalette(HBITMAP__ * *,HPALETTE__ * *)
0x18007b45e  mov     ebx, eax
0x18007b460  test    eax, eax
0x18007b462  js      short loc_18007B4A2
0x18007b464  mov     rax, [rbp+hMem]
0x18007b468  test    rax, rax
0x18007b46b  jz      short loc_18007B481
0x18007b46d  mov     rdx, rax; hMem
0x18007b470  mov     ecx, edi; uFormat
0x18007b472  call    cs:__imp_SetClipboardData
0x18007b478  test    rax, rax
0x18007b47b  jz      loc_18007B234
0x18007b481  mov     rdx, [rbp+var_18]; hMem
0x18007b485  test    rdx, rdx
0x18007b488  jz      short loc_18007B49F
0x18007b48a  mov     ecx, 9; uFormat
0x18007b48f  call    cs:__imp_SetClipboardData
0x18007b495  mov     ebx, 8007000Eh
0x18007b49a  test    rax, rax
0x18007b49d  jz      short loc_18007B4A2
0x18007b49f  mov     ebx, r15d
0x18007b4a2  call    cs:__imp_CloseClipboard
0x18007b4a8  test    r14d, r14d
0x18007b4ab  jz      short loc_18007B4BB
0x18007b4ad  test    rsi, rsi
0x18007b4b0  jz      short loc_18007B4BB
0x18007b4b2  mov     rax, [rsi]
0x18007b4b5  mov     rcx, rsi
0x18007b4b8  call    qword ptr [rax+10h]
0x18007b4bb  mov     eax, ebx
0x18007b4bd  mov     rbx, [rsp+40h+arg_0]
0x18007b4c2  add     rsp, 40h
0x18007b4c6  pop     r15
0x18007b4c8  pop     r14
0x18007b4ca  pop     rdi
0x18007b4cb  pop     rsi
0x18007b4cc  pop     rbp
0x18007b4cd  retn
```
