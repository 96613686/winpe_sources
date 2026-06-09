# DibCreatePalette

- ea: `0x180005384`
- end: `0x180005467`
- name: `DibCreatePalette`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800049d0`

## callees

- `0x180005384`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005403`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005403`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000545c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000545c`
- `GDI32!CreatePalette` at `0x180005450`
- `GDI32!CreatePalette` at `0x180005450`
- `GDI32!CreateHalftonePalette` at `0x1800053cb`
- `GDI32!CreateHalftonePalette` at `0x1800053cb`
- `USER32!ReleaseDC` at `0x1800053d9`
- `USER32!ReleaseDC` at `0x1800053d9`
- `USER32!GetDC` at `0x1800053bf`
- `USER32!GetDC` at `0x1800053bf`

## pseudocode

```c
HPALETTE __fastcall DibCreatePalette(int *a1)
{
  int v3; // ebx
  unsigned __int16 v4; // cx
  HDC DC; // rbx
  HPALETTE Palette; // rbp
  __int64 v7; // r14
  LOGPALETTE *v8; // rax
  LOGPALETTE *v9; // rsi
  __int64 v10; // r8
  BYTE *v11; // rcx
  BYTE v12; // al

  if ( !a1 )
    return 0;
  v3 = a1[8];
  if ( !v3 )
  {
    v4 = *((_WORD *)a1 + 7);
    if ( v4 <= 8u )
      v3 = 1 << v4;
  }
  if ( v3 != 3 )
  {
    if ( v3 <= 0 )
      goto LABEL_8;
LABEL_11:
    v7 = *a1;
    Palette = 0;
    v8 = (LOGPALETTE *)LocalAlloc(0x40u, 4LL * (unsigned int)v3 + 8);
    v9 = v8;
    if ( v8 )
    {
      v10 = 0;
      v8->palNumEntries = v3;
      v8->palVersion = 768;
      v11 = (BYTE *)a1 + v7;
      do
      {
        v9->palPalEntry[v10].peRed = v11[2];
        v9->palPalEntry[v10].peGreen = v11[1];
        v12 = *v11;
        v11 += 4;
        v9->palPalEntry[v10].peBlue = v12;
        v9->palPalEntry[v10].peFlags = 0;
        v10 = (unsigned int)(v10 + 1);
      }
      while ( (int)v10 < v3 );
      Palette = CreatePalette(v9);
      LocalFree(v9);
    }
    return Palette;
  }
  if ( a1[4] != 3 )
    goto LABEL_11;
LABEL_8:
  DC = GetDC(0);
  Palette = CreateHalftonePalette(DC);
  ReleaseDC(0, DC);
  return Palette;
}

```

## disassembly

```asm
0x180005384  push    rbx
0x180005386  push    rbp
0x180005387  push    rsi
0x180005388  push    rdi
0x180005389  push    r14
0x18000538b  sub     rsp, 20h
0x18000538f  mov     rdi, rcx
0x180005392  test    rcx, rcx
0x180005395  jnz     short loc_18000539B
0x180005397  xor     eax, eax
0x180005399  jmp     short loc_1800053E2
0x18000539b  mov     ebx, [rcx+20h]
0x18000539e  test    ebx, ebx
0x1800053a0  jnz     short loc_1800053B3
0x1800053a2  movzx   ecx, word ptr [rcx+0Eh]
0x1800053a6  cmp     cx, 8
0x1800053aa  ja      short loc_1800053B3
0x1800053ac  mov     ebx, 1
0x1800053b1  shl     ebx, cl
0x1800053b3  cmp     ebx, 3
0x1800053b6  jnz     short loc_1800053ED
0x1800053b8  cmp     [rdi+10h], ebx
0x1800053bb  jnz     short loc_1800053F1
0x1800053bd  xor     ecx, ecx; hWnd
0x1800053bf  call    cs:__imp_GetDC
0x1800053c5  mov     rcx, rax; hdc
0x1800053c8  mov     rbx, rax
0x1800053cb  call    cs:__imp_CreateHalftonePalette
0x1800053d1  mov     rdx, rbx; hDC
0x1800053d4  xor     ecx, ecx; hWnd
0x1800053d6  mov     rbp, rax
0x1800053d9  call    cs:__imp_ReleaseDC
0x1800053df  mov     rax, rbp
0x1800053e2  add     rsp, 20h
0x1800053e6  pop     r14
0x1800053e8  pop     rdi
0x1800053e9  pop     rsi
0x1800053ea  pop     rbp
0x1800053eb  pop     rbx
0x1800053ec  retn
0x1800053ed  test    ebx, ebx
0x1800053ef  jle     short loc_1800053BD
0x1800053f1  movsxd  r14, dword ptr [rdi]
0x1800053f4  xor     ebp, ebp
0x1800053f6  mov     edx, ebx
0x1800053f8  lea     ecx, [rbp+40h]; uFlags
0x1800053fb  lea     rdx, ds:8[rdx*4]; uBytes
0x180005403  call    cs:__imp_LocalAlloc
0x180005409  mov     rsi, rax
0x18000540c  test    rax, rax
0x18000540f  jz      short loc_1800053DF
0x180005411  xor     r8d, r8d
0x180005414  mov     [rax+2], bx
0x180005418  mov     word ptr [rax], 300h
0x18000541d  lea     rcx, [rdi+r14]
0x180005421  test    ebx, ebx
0x180005423  jz      short loc_18000544D
0x180005425  mov     al, [rcx+2]
0x180005428  mov     [rsi+r8*4+4], al
0x18000542d  mov     al, [rcx+1]
0x180005430  mov     [rsi+r8*4+5], al
0x180005435  mov     al, [rcx]
0x180005437  lea     rcx, [rcx+4]
0x18000543b  mov     [rsi+r8*4+6], al
0x180005440  mov     [rsi+r8*4+7], bpl
0x180005445  inc     r8d
0x180005448  cmp     r8d, ebx
0x18000544b  jl      short loc_180005425
0x18000544d  mov     rcx, rsi; plpal
0x180005450  call    cs:__imp_CreatePalette
0x180005456  mov     rcx, rsi; hMem
0x180005459  mov     rbp, rax
0x18000545c  call    cs:__imp_LocalFree
0x180005462  jmp     loc_1800053DF
```
