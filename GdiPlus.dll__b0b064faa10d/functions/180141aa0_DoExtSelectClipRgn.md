# DoExtSelectClipRgn

- ea: `0x180141aa0`
- end: `0x180141d2f`
- name: `DoExtSelectClipRgn`
- size: `655`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18013f410`

## callees

- `0x1800c1bd4`
- `0x1800c1e78`
- `0x1800c2404`
- `0x1800c42f4`
- `0x1800c4b24`
- `0x1800ec47c`
- `0x18013e940`
- `0x18013ea74`
- `0x180141aa0`
- `0x180142914`

## import_xrefs

- `GDI32!ExtCreateRegion` at `0x180141ce5`
- `GDI32!ExtCreateRegion` at `0x180141ce5`
- `GDI32!ExtSelectClipRgn` at `0x180141c49`
- `GDI32!ExtSelectClipRgn` at `0x180141ca0`
- `GDI32!ExtSelectClipRgn` at `0x180141cfd`
- `GDI32!ExtSelectClipRgn` at `0x180141c49`
- `GDI32!ExtSelectClipRgn` at `0x180141ca0`
- `GDI32!ExtSelectClipRgn` at `0x180141cfd`
- `GDI32!DeleteObject` at `0x180141cab`
- `GDI32!DeleteObject` at `0x180141d08`
- `GDI32!DeleteObject` at `0x180141cab`
- `GDI32!DeleteObject` at `0x180141d08`
- `GDI32!CreateRectRgn` at `0x180141c81`
- `GDI32!CreateRectRgn` at `0x180141c81`

## pseudocode

```c
__int64 __fastcall DoExtSelectClipRgn(__int64 a1, DWORD a2, const RGNDATA *a3, int a4)
{
  int v4; // eax
  unsigned int v9; // eax
  unsigned int v10; // ebp
  int v11; // eax
  __int64 v13; // rdx
  int v14; // r15d
  int v15; // ecx
  HRGN RectRgn; // rax
  HRGN v17; // r15
  int v18; // ebx
  const XFORM *v19; // rcx
  HRGN Region; // rax
  HRGN v21; // rbp
  int v22; // ebx
  __int16 v23; // [rsp+90h] [rbp+8h] BYREF

  v4 = *(_DWORD *)(a1 + 484);
  if ( v4 == 1 )
  {
    *(_DWORD *)(a1 + 484) = 2;
    if ( (unsigned int)DoRemoveObjects() )
    {
      DoRestoreDC(a1, (unsigned int)(*(_DWORD *)(a1 + 488) - *(_DWORD *)(a1 + 452)));
      v9 = DoMoveTo(a1, *(unsigned int *)(a1 + 476), *(unsigned int *)(a1 + 480));
      v23 = 0;
      v10 = v9;
      if ( (unsigned int)bEmitWin16Escape(a1, 38, 2, &v23) )
      {
        v23 = 0;
        v11 = bEmitWin16Escape(a1, 4097, 2, &v23);
        goto LABEL_5;
      }
    }
    return 0;
  }
  v23 = 1;
  if ( v4 == 3 )
  {
    v13 = *(unsigned int *)(a1 + 472);
    *(_DWORD *)(a1 + 484) = 0;
    *(_QWORD *)(a1 + 528) = 0;
    v10 = DoSetRop2(a1, v13);
    if ( (unsigned int)bEmitWin16Escape(a1, 4097, 2, &v23) )
    {
      v11 = bW16Emit5(a1, 1574, 263, 20560, 20052, 6, 15);
LABEL_5:
      if ( v11 )
        return v10;
    }
    return 0;
  }
  v14 = bNoDCRgn(a1, 1);
  if ( *(int *)(a1 + 456) > 0 )
  {
    do
    {
      bEmitWin16Escape(a1, 4097, 2, &v23);
      v15 = *(_DWORD *)(a1 + 456) - 1;
      *(_DWORD *)(a1 + 456) = v15;
    }
    while ( v15 > 0 );
  }
  if ( a2 )
  {
    if ( v14 )
    {
      if ( (unsigned int)(a4 - 2) <= 2 )
      {
        RectRgn = CreateRectRgn(-32768, -32768, 0x7FFF, 0x7FFF);
        v17 = RectRgn;
        if ( !RectRgn )
          return 0;
        v18 = ExtSelectClipRgn(*(HDC *)(a1 + 40), RectRgn, 5);
        DeleteObject(v17);
        if ( !v18 )
          return 0;
      }
    }
    if ( pfnSetVirtualResolution )
    {
      v19 = 0;
    }
    else
    {
      if ( a2 < 0x20 || a3->rdh.rcBound.left > a3->rdh.rcBound.right || a3->rdh.rcBound.top > a3->rdh.rcBound.bottom )
        return 0;
      v19 = (const XFORM *)(a1 + 300);
    }
    Region = ExtCreateRegion(v19, a2, a3);
    v21 = Region;
    if ( Region )
    {
      v22 = ExtSelectClipRgn(*(HDC *)(a1 + 40), Region, a4);
      DeleteObject(v21);
      if ( v22 )
        return bDumpDCClipping(a1);
    }
    return 0;
  }
  if ( v14 )
    return 1;
  ExtSelectClipRgn(*(HDC *)(a1 + 40), 0, a4);
  return bW16Emit1(a1, 300, 0);
}

```

## disassembly

```asm
0x180141aa0  push    rbx
0x180141aa2  push    rbp
0x180141aa3  push    rsi
0x180141aa4  push    rdi
0x180141aa5  push    r12
0x180141aa7  push    r13
0x180141aa9  push    r14
0x180141aab  push    r15
0x180141aad  sub     rsp, 48h
0x180141ab1  mov     eax, [rcx+1E4h]
0x180141ab7  mov     r12d, 1
0x180141abd  mov     r13d, r9d
0x180141ac0  mov     rbp, r8
0x180141ac3  mov     r14d, edx
0x180141ac6  mov     rdi, rcx
0x180141ac9  cmp     eax, r12d
0x180141acc  jnz     loc_180141B6C
0x180141ad2  lea     ebx, [r12+1]
0x180141ad7  mov     [rcx+1E4h], ebx
0x180141add  call    DoRemoveObjects
0x180141ae2  xor     esi, esi
0x180141ae4  test    eax, eax
0x180141ae6  jz      loc_180141D1C
0x180141aec  mov     edx, [rdi+1E8h]
0x180141af2  mov     rcx, rdi
0x180141af5  sub     edx, [rdi+1C4h]
0x180141afb  call    DoRestoreDC
0x180141b00  mov     r8d, [rdi+1E0h]
0x180141b07  mov     rcx, rdi
0x180141b0a  mov     edx, [rdi+1DCh]
0x180141b10  call    DoMoveTo
0x180141b15  mov     r8d, ebx
0x180141b18  mov     [rsp+88h+arg_0], si
0x180141b20  lea     edx, [rbx+24h]
0x180141b23  mov     rcx, rdi
0x180141b26  lea     r9, [rsp+88h+arg_0]
0x180141b2e  mov     ebp, eax
0x180141b30  call    bEmitWin16Escape
0x180141b35  test    eax, eax
0x180141b37  jz      loc_180141D1C
0x180141b3d  mov     r8d, ebx
0x180141b40  mov     [rsp+88h+arg_0], si
0x180141b48  mov     edx, 1001h
0x180141b4d  lea     r9, [rsp+88h+arg_0]
0x180141b55  mov     rcx, rdi
0x180141b58  call    bEmitWin16Escape
0x180141b5d  test    eax, eax
0x180141b5f  jz      loc_180141D1C
0x180141b65  mov     eax, ebp
0x180141b67  jmp     loc_180141D1E
0x180141b6c  mov     [rsp+88h+arg_0], r12w
0x180141b75  cmp     eax, 3
0x180141b78  jnz     short loc_180141BEA
0x180141b7a  mov     edx, [rcx+1D8h]
0x180141b80  xor     esi, esi
0x180141b82  mov     [rcx+1E4h], esi
0x180141b88  mov     [rcx+210h], rsi
0x180141b8f  call    DoSetRop2
0x180141b94  mov     edx, 1001h
0x180141b99  lea     r8d, [rsi+2]
0x180141b9d  lea     r9, [rsp+88h+arg_0]
0x180141ba5  mov     rcx, rdi
0x180141ba8  mov     ebp, eax
0x180141baa  call    bEmitWin16Escape
0x180141baf  test    eax, eax
0x180141bb1  jz      loc_180141D1C
0x180141bb7  mov     [rsp+88h+var_58], 0Fh
0x180141bbe  mov     edx, 626h
0x180141bc3  mov     [rsp+88h+var_60], 6
0x180141bca  mov     r9d, 5050h
0x180141bd0  mov     r8d, 107h
0x180141bd6  mov     [rsp+88h+var_68], 4E54h
0x180141bdd  mov     rcx, rdi
0x180141be0  call    bW16Emit5
0x180141be5  jmp     loc_180141B5D
0x180141bea  mov     edx, r12d
0x180141bed  call    bNoDCRgn
0x180141bf2  xor     esi, esi
0x180141bf4  mov     r15d, eax
0x180141bf7  mov     ebx, 2
0x180141bfc  cmp     [rdi+1C8h], esi
0x180141c02  jle     short loc_180141C2E
0x180141c04  mov     r8d, ebx
0x180141c07  lea     r9, [rsp+88h+arg_0]
0x180141c0f  mov     edx, 1001h
0x180141c14  mov     rcx, rdi
0x180141c17  call    bEmitWin16Escape
0x180141c1c  mov     ecx, [rdi+1C8h]
0x180141c22  dec     ecx
0x180141c24  mov     [rdi+1C8h], ecx
0x180141c2a  test    ecx, ecx
0x180141c2c  jg      short loc_180141C04
0x180141c2e  test    r14d, r14d
0x180141c31  jnz     short loc_180141C64
0x180141c33  test    r15d, r15d
0x180141c36  jz      short loc_180141C40
0x180141c38  mov     eax, r12d
0x180141c3b  jmp     loc_180141D1E
0x180141c40  mov     rcx, [rdi+28h]; hdc
0x180141c44  mov     r8d, r13d; mode
0x180141c47  xor     edx, edx; hrgn
0x180141c49  call    cs:__imp_ExtSelectClipRgn
0x180141c4f  xor     r8d, r8d
0x180141c52  mov     edx, 12Ch
0x180141c57  mov     rcx, rdi
0x180141c5a  call    bW16Emit1
0x180141c5f  jmp     loc_180141D1E
0x180141c64  test    r15d, r15d
0x180141c67  jz      short loc_180141CB5
0x180141c69  lea     eax, [r13-2]
0x180141c6d  cmp     eax, ebx
0x180141c6f  ja      short loc_180141CB5
0x180141c71  mov     r8d, 7FFFh; x2
0x180141c77  mov     ecx, 0FFFF8000h; x1
0x180141c7c  mov     r9d, r8d; y2
0x180141c7f  mov     edx, ecx; y1
0x180141c81  call    cs:__imp_CreateRectRgn
0x180141c87  mov     r15, rax
0x180141c8a  test    rax, rax
0x180141c8d  jz      loc_180141D1C
0x180141c93  mov     rcx, [rdi+28h]; hdc
0x180141c97  mov     r8d, 5; mode
0x180141c9d  mov     rdx, rax; hrgn
0x180141ca0  call    cs:__imp_ExtSelectClipRgn
0x180141ca6  mov     rcx, r15; ho
0x180141ca9  mov     ebx, eax
0x180141cab  call    cs:__imp_DeleteObject
0x180141cb1  test    ebx, ebx
0x180141cb3  jz      short loc_180141D1C
0x180141cb5  cmp     cs:pfnSetVirtualResolution, rsi
0x180141cbc  jz      short loc_180141CC2
0x180141cbe  xor     ecx, ecx
0x180141cc0  jmp     short loc_180141CDF
0x180141cc2  cmp     r14d, 20h ; ' '
0x180141cc6  jb      short loc_180141D1C
0x180141cc8  mov     eax, [rbp+18h]
0x180141ccb  cmp     [rbp+10h], eax
0x180141cce  jg      short loc_180141D1C
0x180141cd0  mov     eax, [rbp+1Ch]
0x180141cd3  cmp     [rbp+14h], eax
0x180141cd6  jg      short loc_180141D1C
0x180141cd8  lea     rcx, [rdi+12Ch]; lpx
0x180141cdf  mov     r8, rbp; lpData
0x180141ce2  mov     edx, r14d; nCount
0x180141ce5  call    cs:__imp_ExtCreateRegion
0x180141ceb  mov     rbp, rax
0x180141cee  test    rax, rax
0x180141cf1  jz      short loc_180141D1C
0x180141cf3  mov     rcx, [rdi+28h]; hdc
0x180141cf7  mov     r8d, r13d; mode
0x180141cfa  mov     rdx, rax; hrgn
0x180141cfd  call    cs:__imp_ExtSelectClipRgn
0x180141d03  mov     rcx, rbp; ho
0x180141d06  mov     ebx, eax
0x180141d08  call    cs:__imp_DeleteObject
0x180141d0e  test    ebx, ebx
0x180141d10  jz      short loc_180141D1C
0x180141d12  mov     rcx, rdi
0x180141d15  call    bDumpDCClipping
0x180141d1a  jmp     short loc_180141D1E
0x180141d1c  xor     eax, eax
0x180141d1e  add     rsp, 48h
0x180141d22  pop     r15
0x180141d24  pop     r14
0x180141d26  pop     r13
0x180141d28  pop     r12
0x180141d2a  pop     rdi
0x180141d2b  pop     rsi
0x180141d2c  pop     rbp
0x180141d2d  pop     rbx
0x180141d2e  retn
```
