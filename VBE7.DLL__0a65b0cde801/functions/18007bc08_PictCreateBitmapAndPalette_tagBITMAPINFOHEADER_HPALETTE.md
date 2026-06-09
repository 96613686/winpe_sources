# _PictCreateBitmapAndPalette(tagBITMAPINFOHEADER *,HPALETTE__ * *)

- ea: `0x18007bc08`
- end: `0x18007bd06`
- name: `?_PictCreateBitmapAndPalette@@YAPEAUHBITMAP__@@PEAUtagBITMAPINFOHEADER@@PEAPEAUHPALETTE__@@@Z`
- size: `254`
- prototype: `HBITMAP __fastcall(struct tagBITMAPINFOHEADER *, HPALETTE *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18007a9bc`
- `0x18007bd0c`

## callees

- `0x18007bc08`
- `0x18007c1d0`
- `0x18007c860`
- `0x180379380`

## import_xrefs

- `USER32!GetDC` at `0x18007bc35`
- `USER32!GetDC` at `0x18007bc35`
- `USER32!ReleaseDC` at `0x18007bce4`
- `USER32!ReleaseDC` at `0x18007bce4`
- `GDI32!CreateDIBitmap` at `0x18007bc9a`
- `GDI32!CreateDIBitmap` at `0x18007bc9a`
- `GDI32!SelectPalette` at `0x18007bc5f`
- `GDI32!SelectPalette` at `0x18007bcba`
- `GDI32!SelectPalette` at `0x18007bc5f`
- `GDI32!SelectPalette` at `0x18007bcba`
- `GDI32!RealizePalette` at `0x18007bc6b`
- `GDI32!RealizePalette` at `0x18007bcc3`
- `GDI32!RealizePalette` at `0x18007bc6b`
- `GDI32!RealizePalette` at `0x18007bcc3`
- `GDI32!DeleteObject` at `0x18007bcd6`
- `GDI32!DeleteObject` at `0x18007bcd6`

## pseudocode

```c
HBITMAP __fastcall _PictCreateBitmapAndPalette(BITMAPINFO *a1, HPALETTE *a2)
{
  HPALETTE v4; // rbx
  HPALETTE v5; // rsi
  HDC DC; // rdi
  HPALETTE DIBPalette; // rax
  unsigned int v8; // eax
  HBITMAP DIBitmap; // rbp

  v4 = 0;
  v5 = 0;
  DC = GetDC(0);
  if ( Sys_ScrSizePalette )
  {
    DIBPalette = _PictCreateDIBPalette(&a1->bmiHeader);
    v4 = DIBPalette;
    if ( DIBPalette )
    {
      v5 = SelectPalette(DC, DIBPalette, 0);
      RealizePalette(DC);
    }
  }
  v8 = _PictPaletteSize(&a1->bmiHeader);
  DIBitmap = CreateDIBitmap(DC, &a1->bmiHeader, 4u, (char *)a1 + v8 + a1->bmiHeader.biSize, a1, 0);
  if ( Sys_ScrSizePalette )
  {
    if ( v5 )
    {
      SelectPalette(DC, v5, 0);
      RealizePalette(DC);
    }
    if ( !DIBitmap && v4 )
      DeleteObject(v4);
  }
  *a2 = v4;
  ReleaseDC(0, DC);
  return DIBitmap;
}

```

## disassembly

```asm
0x18007bc08  mov     [rsp+arg_0], rbx
0x18007bc0d  mov     [rsp+arg_8], rbp
0x18007bc12  mov     [rsp+arg_10], rsi
0x18007bc17  push    rdi
0x18007bc18  push    r14
0x18007bc1a  push    r15
0x18007bc1c  mov     eax, 30h
0x18007bc21  call    _alloca_probe
0x18007bc26  sub     rsp, rax
0x18007bc29  mov     r14, rcx
0x18007bc2c  xor     ecx, ecx; hWnd
0x18007bc2e  mov     r15, rdx
0x18007bc31  xor     ebx, ebx
0x18007bc33  xor     esi, esi
0x18007bc35  call    cs:__imp_GetDC
0x18007bc3b  cmp     cs:?Sys_ScrSizePalette@@3IA, ebx; uint Sys_ScrSizePalette
0x18007bc41  mov     rdi, rax
0x18007bc44  jz      short loc_18007BC71
0x18007bc46  mov     rcx, r14; struct tagBITMAPINFOHEADER *
0x18007bc49  call    ?_PictCreateDIBPalette@@YAPEAUHPALETTE__@@PEAUtagBITMAPINFOHEADER@@@Z; _PictCreateDIBPalette(tagBITMAPINFOHEADER *)
0x18007bc4e  mov     rbx, rax
0x18007bc51  test    rax, rax
0x18007bc54  jz      short loc_18007BC71
0x18007bc56  xor     r8d, r8d; bForceBkgd
0x18007bc59  mov     rdx, rax; hPal
0x18007bc5c  mov     rcx, rdi; hdc
0x18007bc5f  call    cs:__imp_SelectPalette
0x18007bc65  mov     rcx, rdi; hdc
0x18007bc68  mov     rsi, rax
0x18007bc6b  call    cs:__imp_RealizePalette
0x18007bc71  mov     rcx, r14; struct tagBITMAPINFOHEADER *
0x18007bc74  call    ?_PictPaletteSize@@YAIPEAUtagBITMAPINFOHEADER@@@Z; _PictPaletteSize(tagBITMAPINFOHEADER *)
0x18007bc79  mov     r9d, [r14]
0x18007bc7c  and     [rsp+48h+var_20], 0
0x18007bc81  mov     ecx, eax
0x18007bc83  mov     r8d, 4; flInit
0x18007bc89  mov     rdx, r14; pbmih
0x18007bc8c  add     rcx, r14
0x18007bc8f  mov     [rsp+48h+pbmi], r14; pbmi
0x18007bc94  add     r9, rcx; pjBits
0x18007bc97  mov     rcx, rdi; hdc
0x18007bc9a  call    cs:__imp_CreateDIBitmap
0x18007bca0  cmp     cs:?Sys_ScrSizePalette@@3IA, 0; uint Sys_ScrSizePalette
0x18007bca7  mov     rbp, rax
0x18007bcaa  jz      short loc_18007BCDC
0x18007bcac  test    rsi, rsi
0x18007bcaf  jz      short loc_18007BCC9
0x18007bcb1  xor     r8d, r8d; bForceBkgd
0x18007bcb4  mov     rdx, rsi; hPal
0x18007bcb7  mov     rcx, rdi; hdc
0x18007bcba  call    cs:__imp_SelectPalette
0x18007bcc0  mov     rcx, rdi; hdc
0x18007bcc3  call    cs:__imp_RealizePalette
0x18007bcc9  test    rbp, rbp
0x18007bccc  jnz     short loc_18007BCDC
0x18007bcce  test    rbx, rbx
0x18007bcd1  jz      short loc_18007BCDC
0x18007bcd3  mov     rcx, rbx; ho
0x18007bcd6  call    cs:__imp_DeleteObject
0x18007bcdc  mov     rdx, rdi; hDC
0x18007bcdf  xor     ecx, ecx; hWnd
0x18007bce1  mov     [r15], rbx
0x18007bce4  call    cs:__imp_ReleaseDC
0x18007bcea  mov     rbx, [rsp+48h+arg_0]
0x18007bcef  mov     rsi, [rsp+48h+arg_10]
0x18007bcf4  mov     rax, rbp
0x18007bcf7  mov     rbp, [rsp+48h+arg_8]
0x18007bcfc  add     rsp, 30h
0x18007bd00  pop     r15
0x18007bd02  pop     r14
0x18007bd04  pop     rdi
0x18007bd05  retn
```
