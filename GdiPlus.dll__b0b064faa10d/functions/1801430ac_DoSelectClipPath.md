# DoSelectClipPath

- ea: `0x1801430ac`
- end: `0x180143324`
- name: `DoSelectClipPath`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18013fdd0`

## callees

- `0x1800c1bd4`
- `0x1800c2404`
- `0x1800c42f4`
- `0x1800c49e8`
- `0x18013e940`
- `0x18013ea74`
- `0x18014296c`
- `0x1801430ac`

## import_xrefs

- `GDI32!SelectClipPath` at `0x1801432dd`
- `GDI32!SelectClipPath` at `0x1801432dd`
- `GDI32!ExtSelectClipRgn` at `0x1801432be`
- `GDI32!ExtSelectClipRgn` at `0x1801432be`
- `GDI32!MoveToEx` at `0x1801431b2`
- `GDI32!MoveToEx` at `0x1801431c8`
- `GDI32!MoveToEx` at `0x1801431b2`
- `GDI32!MoveToEx` at `0x1801431c8`
- `GDI32!SetROP2` at `0x180143185`
- `GDI32!SetROP2` at `0x180143185`
- `GDI32!GetROP2` at `0x18014311d`
- `GDI32!GetROP2` at `0x18014311d`
- `GDI32!DeleteObject` at `0x1801432c9`
- `GDI32!DeleteObject` at `0x1801432c9`
- `GDI32!CreateRectRgn` at `0x18014329f`
- `GDI32!CreateRectRgn` at `0x18014329f`

## pseudocode

```c
__int64 __fastcall DoSelectClipPath(__int64 a1, int a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  HDC v7; // rcx
  int ROP2; // eax
  int v9; // ebx
  __int64 result; // rax
  int v11; // r14d
  HRGN RectRgn; // rax
  HRGN v13; // rbp
  int v14; // ebx
  __int16 v15; // [rsp+68h] [rbp+10h] BYREF

  v4 = bNoDCRgn(a1, 1);
  v5 = v4;
  if ( (((a2 - 1) & 0xFFFFFFFB) == 0 || a2 == 2 && v4) && (*(_BYTE *)(a1 + 4) & 0x10) != 0 )
  {
    v6 = *(_DWORD *)(a1 + 484);
    switch ( v6 )
    {
      case 0:
        v7 = *(HDC *)(a1 + 40);
        *(_DWORD *)(a1 + 488) = *(_DWORD *)(a1 + 452);
        *(_DWORD *)(a1 + 484) = 1;
        ROP2 = GetROP2(v7);
        v9 = ROP2;
        if ( ROP2 != 13 && ROP2 != 4 )
        {
          *(_DWORD *)(a1 + 4) |= 0x40000000u;
          return 0;
        }
        if ( !(unsigned int)DoSaveDC(a1) )
          return 0;
        *(_DWORD *)(a1 + 472) = v9;
        v15 = 1;
        if ( !(unsigned int)bEmitWin16Escape(a1, 38, 2, &v15) )
          return 0;
        SetROP2(*(HDC *)(a1 + 40), 7);
        if ( !(unsigned int)bW16Emit1(a1, 260, 7) )
          return 0;
        MoveToEx(*(HDC *)(a1 + 40), 0, 0, (LPPOINT)(a1 + 476));
        MoveToEx(*(HDC *)(a1 + 40), *(_DWORD *)(a1 + 476), *(_DWORD *)(a1 + 480), 0);
        *(_QWORD *)(a1 + 536) = *(_QWORD *)(a1 + 504);
        return 1;
      case 1:
        *(_QWORD *)(a1 + 536) = *(_QWORD *)(a1 + 504);
        return 1;
      case 3:
        return (unsigned int)ConvertPathToPSClipPath(a1, 0)
            && (unsigned int)bW16Emit5(a1, 1574, 262, 20560, 20052, 6, 15);
    }
  }
  v11 = 0;
  if ( (unsigned int)ConvertPathToPSClipPath(a1, 1) )
  {
    ++*(_DWORD *)(a1 + 456);
    v15 = 1;
    v11 = 1;
    if ( !(unsigned int)bEmitWin16Escape(a1, 38, 2, &v15) )
      return 0;
  }
  if ( (unsigned int)(a2 - 2) <= 2 )
  {
    if ( v5 )
    {
      RectRgn = CreateRectRgn(-32768, -32768, 0x7FFF, 0x7FFF);
      v13 = RectRgn;
      if ( !RectRgn )
        return 0;
      v14 = ExtSelectClipRgn(*(HDC *)(a1 + 40), RectRgn, 5);
      DeleteObject(v13);
      if ( !v14 )
        return 0;
    }
  }
  if ( !SelectClipPath(*(HDC *)(a1 + 40), a2) )
    return 0;
  result = bDumpDCClipping(a1);
  if ( v11 )
  {
    v15 = 0;
    return (unsigned int)bEmitWin16Escape(a1, 38, 2, &v15) != 0 ? (unsigned int)result : 0;
  }
  return result;
}

```

## disassembly

```asm
0x1801430ac  mov     [rsp+arg_0], rbx
0x1801430b1  mov     [rsp+arg_10], rbp
0x1801430b6  push    rsi
0x1801430b7  push    rdi
0x1801430b8  push    r14
0x1801430ba  sub     rsp, 40h
0x1801430be  mov     esi, edx
0x1801430c0  mov     ebp, 1
0x1801430c5  mov     edx, ebp
0x1801430c7  mov     rdi, rcx
0x1801430ca  call    bNoDCRgn
0x1801430cf  lea     r8d, [rsi-1]
0x1801430d3  mov     ebx, eax
0x1801430d5  test    r8d, 0FFFFFFFBh
0x1801430dc  jz      short loc_1801430EF
0x1801430de  cmp     esi, 2
0x1801430e1  jnz     loc_180143246
0x1801430e7  test    eax, eax
0x1801430e9  jz      loc_180143246
0x1801430ef  test    byte ptr [rdi+4], 10h
0x1801430f3  jz      loc_180143246
0x1801430f9  mov     eax, [rdi+1E4h]
0x1801430ff  test    eax, eax
0x180143101  jnz     loc_1801431E3
0x180143107  mov     eax, [rdi+1C4h]
0x18014310d  mov     rcx, [rdi+28h]; hdc
0x180143111  mov     [rdi+1E8h], eax
0x180143117  mov     [rdi+1E4h], ebp
0x18014311d  call    cs:__imp_GetROP2
0x180143123  mov     ebx, eax
0x180143125  cmp     eax, 0Dh
0x180143128  jz      short loc_180143149
0x18014312a  cmp     eax, 4
0x18014312d  jz      short loc_180143149
0x18014312f  bts     dword ptr [rdi+4], 1Eh
0x180143134  xor     eax, eax
0x180143136  mov     rbx, [rsp+58h+arg_0]
0x18014313b  mov     rbp, [rsp+58h+arg_10]
0x180143140  add     rsp, 40h
0x180143144  pop     r14
0x180143146  pop     rdi
0x180143147  pop     rsi
0x180143148  retn
0x180143149  mov     rcx, rdi
0x18014314c  call    DoSaveDC
0x180143151  test    eax, eax
0x180143153  jz      short loc_180143134
0x180143155  mov     edx, 26h ; '&'
0x18014315a  mov     [rdi+1D8h], ebx
0x180143160  lea     r9, [rsp+58h+arg_8]
0x180143165  mov     [rsp+58h+arg_8], bp
0x18014316a  mov     rcx, rdi
0x18014316d  lea     r8d, [rdx-24h]
0x180143171  call    bEmitWin16Escape
0x180143176  test    eax, eax
0x180143178  jz      short loc_180143134
0x18014317a  mov     rcx, [rdi+28h]; hdc
0x18014317e  mov     ebx, 7
0x180143183  mov     edx, ebx; rop2
0x180143185  call    cs:__imp_SetROP2
0x18014318b  mov     r8d, ebx
0x18014318e  mov     edx, 104h
0x180143193  mov     rcx, rdi
0x180143196  call    bW16Emit1
0x18014319b  test    eax, eax
0x18014319d  jz      short loc_180143134
0x18014319f  mov     rcx, [rdi+28h]; hdc
0x1801431a3  lea     rbx, [rdi+1DCh]
0x1801431aa  mov     r9, rbx; lppt
0x1801431ad  xor     r8d, r8d; y
0x1801431b0  xor     edx, edx; x
0x1801431b2  call    cs:__imp_MoveToEx
0x1801431b8  mov     r8d, [rdi+1E0h]; y
0x1801431bf  xor     r9d, r9d; lppt
0x1801431c2  mov     edx, [rbx]; x
0x1801431c4  mov     rcx, [rdi+28h]; hdc
0x1801431c8  call    cs:__imp_MoveToEx
0x1801431ce  mov     rcx, [rdi+1F8h]
0x1801431d5  mov     [rdi+218h], rcx
0x1801431dc  mov     eax, ebp
0x1801431de  jmp     loc_180143136
0x1801431e3  cmp     eax, ebp
0x1801431e5  jnz     short loc_1801431F7
0x1801431e7  mov     rax, [rdi+1F8h]
0x1801431ee  mov     [rdi+218h], rax
0x1801431f5  jmp     short loc_1801431DC
0x1801431f7  cmp     eax, 3
0x1801431fa  jnz     short loc_180143246
0x1801431fc  xor     edx, edx
0x1801431fe  mov     rcx, rdi
0x180143201  call    ConvertPathToPSClipPath
0x180143206  test    eax, eax
0x180143208  jz      loc_180143134
0x18014320e  mov     [rsp+58h+var_28], 0Fh
0x180143215  mov     edx, 626h
0x18014321a  mov     [rsp+58h+var_30], 6
0x180143221  mov     r9d, 5050h
0x180143227  mov     r8d, 106h
0x18014322d  mov     [rsp+58h+var_38], 4E54h
0x180143234  mov     rcx, rdi
0x180143237  call    bW16Emit5
0x18014323c  test    eax, eax
0x18014323e  jz      loc_180143134
0x180143244  jmp     short loc_1801431DC
0x180143246  mov     edx, ebp
0x180143248  mov     rcx, rdi
0x18014324b  xor     r14d, r14d
0x18014324e  call    ConvertPathToPSClipPath
0x180143253  test    eax, eax
0x180143255  jz      short loc_180143283
0x180143257  add     [rdi+1C8h], ebp
0x18014325d  lea     r9, [rsp+58h+arg_8]
0x180143262  mov     edx, 26h ; '&'
0x180143267  mov     [rsp+58h+arg_8], bp
0x18014326c  mov     rcx, rdi
0x18014326f  mov     r14d, ebp
0x180143272  lea     r8d, [rdx-24h]
0x180143276  call    bEmitWin16Escape
0x18014327b  test    eax, eax
0x18014327d  jz      loc_180143134
0x180143283  lea     eax, [rsi-2]
0x180143286  cmp     eax, 2
0x180143289  ja      short loc_1801432D7
0x18014328b  test    ebx, ebx
0x18014328d  jz      short loc_1801432D7
0x18014328f  mov     r8d, 7FFFh; x2
0x180143295  mov     ecx, 0FFFF8000h; x1
0x18014329a  mov     r9d, r8d; y2
0x18014329d  mov     edx, ecx; y1
0x18014329f  call    cs:__imp_CreateRectRgn
0x1801432a5  mov     rbp, rax
0x1801432a8  test    rax, rax
0x1801432ab  jz      loc_180143134
0x1801432b1  mov     rcx, [rdi+28h]; hdc
0x1801432b5  mov     r8d, 5; mode
0x1801432bb  mov     rdx, rax; hrgn
0x1801432be  call    cs:__imp_ExtSelectClipRgn
0x1801432c4  mov     rcx, rbp; ho
0x1801432c7  mov     ebx, eax
0x1801432c9  call    cs:__imp_DeleteObject
0x1801432cf  test    ebx, ebx
0x1801432d1  jz      loc_180143134
0x1801432d7  mov     rcx, [rdi+28h]; hdc
0x1801432db  mov     edx, esi; mode
0x1801432dd  call    cs:__imp_SelectClipPath
0x1801432e3  test    eax, eax
0x1801432e5  jz      loc_180143134
0x1801432eb  mov     rcx, rdi
0x1801432ee  call    bDumpDCClipping
0x1801432f3  mov     ebx, eax
0x1801432f5  test    r14d, r14d
0x1801432f8  jz      loc_180143136
0x1801432fe  xor     ecx, ecx
0x180143300  lea     r9, [rsp+58h+arg_8]
0x180143305  mov     [rsp+58h+arg_8], cx
0x18014330a  lea     edx, [rcx+26h]
0x18014330d  lea     r8d, [rcx+2]
0x180143311  mov     rcx, rdi
0x180143314  call    bEmitWin16Escape
0x180143319  neg     eax
0x18014331b  sbb     eax, eax
0x18014331d  and     eax, ebx
0x18014331f  jmp     loc_180143136
```
