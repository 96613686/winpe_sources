# CCanvas::WrapUpRegion(void)

- ea: `0x18003a6c0`
- end: `0x18003aab7`
- name: `?WrapUpRegion@CCanvas@@UEAAXXZ`
- size: `1015`
- prototype: `void __fastcall(CCanvas *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180037164`
- `0x18003a6c0`
- `0x18003aac0`
- `0x180044ab0`
- `0x180098b18`
- `0x1800993b8`
- `0x180099ca8`

## import_xrefs

- `GDI32!FillRgn` at `0x18003a7c5`
- `GDI32!FillRgn` at `0x18003a7c5`
- `GDI32!PathToRegion` at `0x18003a799`
- `GDI32!PathToRegion` at `0x18003a799`
- `GDI32!ExtSelectClipRgn` at `0x18003a78c`
- `GDI32!ExtSelectClipRgn` at `0x18003a7fb`
- `GDI32!ExtSelectClipRgn` at `0x18003a78c`
- `GDI32!ExtSelectClipRgn` at `0x18003a7fb`
- `GDI32!CombineRgn` at `0x18003a76d`
- `GDI32!CombineRgn` at `0x18003a827`
- `GDI32!CombineRgn` at `0x18003a76d`
- `GDI32!CombineRgn` at `0x18003a827`
- `GDI32!EndPath` at `0x18003a70b`
- `GDI32!EndPath` at `0x18003a70b`
- `GDI32!SetPolyFillMode` at `0x18003a71d`
- `GDI32!SetPolyFillMode` at `0x18003a71d`
- `GDI32!CreateRectRgn` at `0x18003a753`
- `GDI32!CreateRectRgn` at `0x18003a753`
- `GDI32!DeleteObject` at `0x18003a809`
- `GDI32!DeleteObject` at `0x18003a830`
- `GDI32!DeleteObject` at `0x18003a809`
- `GDI32!DeleteObject` at `0x18003a830`
- `gdiplus!GdipFillPath` at `0x18003aa26`
- `gdiplus!GdipFillPath` at `0x18003aa26`
- `gdiplus!GdipFillRegion` at `0x18003a922`
- `gdiplus!GdipFillRegion` at `0x18003a922`
- `gdiplus!GdipResetClip` at `0x18003a937`
- `gdiplus!GdipResetClip` at `0x18003a937`
- `gdiplus!GdipCreateRegion` at `0x18003a97d`
- `gdiplus!GdipCreateRegion` at `0x18003a97d`
- `gdiplus!GdipCreateRegionPath` at `0x18003a8f0`
- `gdiplus!GdipCreateRegionPath` at `0x18003a8f0`
- `gdiplus!GdipDeleteRegion` at `0x18003a9e7`
- `gdiplus!GdipDeleteRegion` at `0x18003a9e7`
- `gdiplus!GdipCombineRegionPath` at `0x18003a9bd`
- `gdiplus!GdipCombineRegionPath` at `0x18003a9bd`
- `gdiplus!GdipSetClipRegion` at `0x18003a8a9`
- `gdiplus!GdipSetClipRegion` at `0x18003a9d7`
- `gdiplus!GdipSetClipRegion` at `0x18003a8a9`
- `gdiplus!GdipSetClipRegion` at `0x18003a9d7`
- `gdiplus!GdipAlloc` at `0x18003a8d3`
- `gdiplus!GdipAlloc` at `0x18003a8d3`

## pseudocode

```c
void __fastcall CCanvas::WrapUpRegion(CCanvas *this)
{
  HDC v2; // rcx
  HRGN RectRgn; // r14
  char v4; // r12
  HRGN v5; // rax
  HRGN v6; // r15
  bool updated; // bl
  HRGN v8; // rcx
  __int64 *v9; // rsi
  _QWORD *v10; // rdx
  __int64 v11; // rbx
  int v12; // eax
  Gdiplus::Region *v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // r14
  int v17; // eax
  __int64 v18; // rbx
  int v19; // eax
  __int64 v20; // r14
  int v21; // r15d
  unsigned int v22; // ebx
  __int64 v23; // rbx
  int v24; // eax
  __int64 v25; // rbx
  int v26; // eax
  __int64 pExceptionObject; // [rsp+70h] [rbp+48h] BYREF

  if ( *((_DWORD *)this + 61) )
  {
    v2 = (HDC)*((_QWORD *)this + 31);
    if ( !v2 )
    {
      LODWORD(pExceptionObject) = -2147467261;
      throw (long *)&pExceptionObject;
    }
    EndPath(v2);
    SetPolyFillMode(*((HDC *)this + 31), 2);
    RectRgn = 0;
    v4 = 0;
    if ( *((_BYTE *)this + 40) && *((_QWORD *)this + 41) )
    {
      if ( *((_QWORD *)this + 14) )
      {
        v4 = 1;
        RectRgn = CreateRectRgn(0, 0, 0, 0);
        CombineRgn(RectRgn, *((HRGN *)this + 41), *((HRGN *)this + 14), 1);
      }
      else
      {
        RectRgn = (HRGN)*((_QWORD *)this + 41);
      }
      ExtSelectClipRgn(*((HDC *)this + 31), *((HRGN *)this + 41), 4);
    }
    v5 = PathToRegion(*((HDC *)this + 31));
    LOBYTE(pExceptionObject) = 1;
    v6 = v5;
    updated = CCanvas::UpdateWorldTransforms(this, (bool *)&pExceptionObject);
    FillRgn(*((HDC *)this + 31), v6, *((HBRUSH *)this + 36));
    if ( updated )
      CCanvas::RestoreWorldTransforms(this, pExceptionObject);
    if ( v6 )
    {
      if ( *((_BYTE *)this + 40) )
      {
        if ( RectRgn )
        {
          ExtSelectClipRgn(*((HDC *)this + 31), RectRgn, 3);
          if ( v4 )
            DeleteObject(RectRgn);
        }
      }
      v8 = (HRGN)*((_QWORD *)this + 41);
      if ( v8 )
      {
        CombineRgn(v8, *((HRGN *)this + 41), v6, 2);
        DeleteObject(v6);
      }
      else
      {
        *((_QWORD *)this + 41) = v6;
      }
    }
LABEL_20:
    *((_BYTE *)this + 240) = 0;
    return;
  }
  if ( !*((_QWORD *)this + 1) || !*((_QWORD *)this + 3) )
  {
    LODWORD(pExceptionObject) = -2147467261;
    throw (long *)&pExceptionObject;
  }
  if ( *((_BYTE *)this + 200) )
  {
    v9 = (__int64 *)((char *)this + 216);
    Gdiplus::GraphicsPath::SetFillMode((char *)this + 216);
    v10 = (_QWORD *)*((_QWORD *)this + 29);
    if ( v10 )
    {
      if ( *((_BYTE *)this + 40) )
      {
        v11 = *((_QWORD *)this + 1);
        v12 = GdipSetClipRegion(*(_QWORD *)v11, *v10, 4);
        if ( v12 )
          *(_DWORD *)(v11 + 8) = v12;
      }
      v13 = (Gdiplus::Region *)*((_QWORD *)this + 29);
      if ( v13 )
        Gdiplus::Region::`scalar deleting destructor'(v13, (unsigned int)v10);
      *((_QWORD *)this + 29) = 0;
    }
    pExceptionObject = GdipAlloc(16);
    v14 = pExceptionObject;
    if ( pExceptionObject )
    {
      v15 = *v9;
      pExceptionObject = 0;
      *(_DWORD *)(v14 + 8) = GdipCreateRegionPath(v15, &pExceptionObject);
      *(_QWORD *)v14 = pExceptionObject;
      *((_QWORD *)this + 29) = v14;
      v16 = *((_QWORD *)this + 1);
      v17 = GdipFillRegion(*(_QWORD *)v16, *(_QWORD *)(*((_QWORD *)this + 3) + 8LL), *(_QWORD *)v14);
      if ( v17 )
        *(_DWORD *)(v16 + 8) = v17;
      v18 = *((_QWORD *)this + 1);
      v19 = GdipResetClip(*(_QWORD *)v18);
      if ( v19 )
        *(_DWORD *)(v18 + 8) = v19;
      Gdiplus::GraphicsPath::Reset(v9);
      goto LABEL_20;
    }
    *((_QWORD *)this + 29) = 0;
  }
  else
  {
    if ( *((_BYTE *)this + 40) && *((int *)this + 51) > 0 )
    {
      pExceptionObject = 0;
      GdipCreateRegion(&pExceptionObject);
      v20 = pExceptionObject;
      v21 = 1;
      v22 = *((_DWORD *)this + 51);
      while ( (--v22 & 0x80000000) == 0 && v21 < 5 )
      {
        GdipCombineRegionPath(v20, *((_QWORD *)this + 2 * (v22 % 5) + 15), 4);
        ++v21;
      }
      v23 = *((_QWORD *)this + 1);
      v24 = GdipSetClipRegion(*(_QWORD *)v23, v20, 0);
      if ( v24 )
        *(_DWORD *)(v23 + 8) = v24;
      GdipDeleteRegion(v20);
    }
    v25 = *((_QWORD *)this + 1);
    v26 = GdipFillPath(
            *(_QWORD *)v25,
            *(_QWORD *)(*((_QWORD *)this + 3) + 8LL),
            *((_QWORD *)this + 2 * (*((_DWORD *)this + 51) % 5) + 15));
    if ( v26 )
      *(_DWORD *)(v25 + 8) = v26;
    if ( *((_BYTE *)this + 40) )
      ++*((_DWORD *)this + 51);
    Gdiplus::GraphicsPath::Reset((char *)this + 16 * (*((_DWORD *)this + 51) % 5) + 120);
    Gdiplus::GraphicsPath::SetFillMode((char *)this + 16 * (*((_DWORD *)this + 51) % 5) + 120);
  }
}

```

## disassembly

```asm
0x18003a6c0  push    rbp
0x18003a6c2  push    rbx
0x18003a6c3  push    rsi
0x18003a6c4  push    rdi
0x18003a6c5  push    r12
0x18003a6c7  push    r13
0x18003a6c9  push    r14
0x18003a6cb  push    r15
0x18003a6cd  mov     rbp, rsp
0x18003a6d0  sub     rsp, 28h
0x18003a6d4  xor     r13d, r13d
0x18003a6d7  mov     rdi, rcx
0x18003a6da  cmp     [rcx+0F4h], r13d
0x18003a6e1  jz      loc_18003A857
0x18003a6e7  mov     rcx, [rcx+0F8h]; hdc
0x18003a6ee  test    rcx, rcx
0x18003a6f1  jnz     short loc_18003A70B
0x18003a6f3  lea     rdx, _TI1J; pThrowInfo
0x18003a6fa  mov     dword ptr [rbp+pExceptionObject], 80004003h
0x18003a701  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003a705  call    _CxxThrowException_0
0x18003a70b  call    cs:__imp_EndPath
0x18003a711  mov     rcx, [rdi+0F8h]; hdc
0x18003a718  mov     edx, 2; mode
0x18003a71d  call    cs:__imp_SetPolyFillMode
0x18003a723  mov     r14, r13
0x18003a726  mov     r12b, r13b
0x18003a729  mov     esi, 1
0x18003a72e  cmp     [rdi+28h], r13b
0x18003a732  jz      short loc_18003A792
0x18003a734  mov     rax, [rdi+148h]
0x18003a73b  test    rax, rax
0x18003a73e  jz      short loc_18003A792
0x18003a740  cmp     [rdi+70h], r13
0x18003a744  jz      short loc_18003A775
0x18003a746  xor     r9d, r9d; y2
0x18003a749  xor     r8d, r8d; x2
0x18003a74c  xor     edx, edx; y1
0x18003a74e  xor     ecx, ecx; x1
0x18003a750  mov     r12b, sil
0x18003a753  call    cs:__imp_CreateRectRgn
0x18003a759  mov     r8, [rdi+70h]; hrgnSrc2
0x18003a75d  mov     r9d, esi; iMode
0x18003a760  mov     rdx, [rdi+148h]; hrgnSrc1
0x18003a767  mov     rcx, rax; hrgnDst
0x18003a76a  mov     r14, rax
0x18003a76d  call    cs:__imp_CombineRgn
0x18003a773  jmp     short loc_18003A778
0x18003a775  mov     r14, rax
0x18003a778  mov     rdx, [rdi+148h]; hrgn
0x18003a77f  mov     r8d, 4; mode
0x18003a785  mov     rcx, [rdi+0F8h]; hdc
0x18003a78c  call    cs:__imp_ExtSelectClipRgn
0x18003a792  mov     rcx, [rdi+0F8h]; hdc
0x18003a799  call    cs:__imp_PathToRegion
0x18003a79f  lea     rdx, [rbp+pExceptionObject]; bool *
0x18003a7a3  mov     byte ptr [rbp+pExceptionObject], sil
0x18003a7a7  mov     rcx, rdi; this
0x18003a7aa  mov     r15, rax
0x18003a7ad  call    ?UpdateWorldTransforms@CCanvas@@IEAA_NAEA_N@Z; CCanvas::UpdateWorldTransforms(bool &)
0x18003a7b2  mov     r8, [rdi+120h]; hbr
0x18003a7b9  mov     rdx, r15; hrgn
0x18003a7bc  mov     rcx, [rdi+0F8h]; hdc
0x18003a7c3  mov     bl, al
0x18003a7c5  call    cs:__imp_FillRgn
0x18003a7cb  cmp     bl, sil
0x18003a7ce  jnz     short loc_18003A7DB
0x18003a7d0  mov     dl, byte ptr [rbp+pExceptionObject]; bool
0x18003a7d3  mov     rcx, rdi; this
0x18003a7d6  call    ?RestoreWorldTransforms@CCanvas@@IEAAX_N@Z; CCanvas::RestoreWorldTransforms(bool)
0x18003a7db  test    r15, r15
0x18003a7de  jz      short loc_18003A83F
0x18003a7e0  cmp     [rdi+28h], r13b
0x18003a7e4  jz      short loc_18003A80F
0x18003a7e6  test    r14, r14
0x18003a7e9  jz      short loc_18003A80F
0x18003a7eb  mov     rcx, [rdi+0F8h]; hdc
0x18003a7f2  mov     r8d, 3; mode
0x18003a7f8  mov     rdx, r14; hrgn
0x18003a7fb  call    cs:__imp_ExtSelectClipRgn
0x18003a801  test    r12b, r12b
0x18003a804  jz      short loc_18003A80F
0x18003a806  mov     rcx, r14; ho
0x18003a809  call    cs:__imp_DeleteObject
0x18003a80f  mov     rcx, [rdi+148h]; hrgnDst
0x18003a816  test    rcx, rcx
0x18003a819  jz      short loc_18003A838
0x18003a81b  mov     r9d, 2; iMode
0x18003a821  mov     r8, r15; hrgnSrc2
0x18003a824  mov     rdx, rcx; hrgnSrc1
0x18003a827  call    cs:__imp_CombineRgn
0x18003a82d  mov     rcx, r15; ho
0x18003a830  call    cs:__imp_DeleteObject
0x18003a836  jmp     short loc_18003A83F
0x18003a838  mov     [rdi+148h], r15
0x18003a83f  mov     [rdi+0F0h], r13b
0x18003a846  add     rsp, 28h
0x18003a84a  pop     r15
0x18003a84c  pop     r14
0x18003a84e  pop     r13
0x18003a850  pop     r12
0x18003a852  pop     rdi
0x18003a853  pop     rsi
0x18003a854  pop     rbx
0x18003a855  pop     rbp
0x18003a856  retn
0x18003a857  cmp     [rcx+8], r13
0x18003a85b  jz      loc_18003AA9F
0x18003a861  cmp     [rcx+18h], r13
0x18003a865  jz      loc_18003AA9F
0x18003a86b  cmp     [rcx+0C8h], r13b
0x18003a872  jz      loc_18003A95D
0x18003a878  lea     rsi, [rcx+0D8h]
0x18003a87f  mov     rcx, rsi
0x18003a882  call    ?SetFillMode@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@W4FillMode@2@@Z; Gdiplus::GraphicsPath::SetFillMode(Gdiplus::FillMode)
0x18003a887  mov     rdx, [rdi+0E8h]
0x18003a88e  test    rdx, rdx
0x18003a891  jz      short loc_18003A8CE
0x18003a893  cmp     [rdi+28h], r13b
0x18003a897  jz      short loc_18003A8B6
0x18003a899  mov     rbx, [rdi+8]
0x18003a89d  mov     r8d, 4
0x18003a8a3  mov     rdx, [rdx]
0x18003a8a6  mov     rcx, [rbx]
0x18003a8a9  call    cs:__imp_GdipSetClipRegion
0x18003a8af  test    eax, eax
0x18003a8b1  jz      short loc_18003A8B6
0x18003a8b3  mov     [rbx+8], eax
0x18003a8b6  mov     rcx, [rdi+0E8h]; this
0x18003a8bd  test    rcx, rcx
0x18003a8c0  jz      short loc_18003A8C7
0x18003a8c2  call    ??_GRegion@Gdiplus@@QEAAPEAXI@Z; Gdiplus::Region::`scalar deleting destructor'(uint)
0x18003a8c7  mov     [rdi+0E8h], r13
0x18003a8ce  mov     ecx, 10h
0x18003a8d3  call    cs:__imp_GdipAlloc
0x18003a8d9  mov     [rbp+pExceptionObject], rax
0x18003a8dd  mov     rbx, rax
0x18003a8e0  test    rax, rax
0x18003a8e3  jz      short loc_18003A951
0x18003a8e5  mov     rcx, [rsi]
0x18003a8e8  lea     rdx, [rbp+pExceptionObject]
0x18003a8ec  mov     [rbp+pExceptionObject], r13
0x18003a8f0  call    cs:__imp_GdipCreateRegionPath
0x18003a8f6  mov     [rbx+8], eax
0x18003a8f9  mov     rax, [rbp+pExceptionObject]
0x18003a8fd  mov     [rbx], rax
0x18003a900  mov     [rdi+0E8h], rbx
0x18003a907  test    rbx, rbx
0x18003a90a  jz      loc_18003A846
0x18003a910  mov     r14, [rdi+8]
0x18003a914  mov     rdx, [rdi+18h]
0x18003a918  mov     r8, [rbx]
0x18003a91b  mov     rcx, [r14]
0x18003a91e  mov     rdx, [rdx+8]
0x18003a922  call    cs:__imp_GdipFillRegion
0x18003a928  test    eax, eax
0x18003a92a  jz      short loc_18003A930
0x18003a92c  mov     [r14+8], eax
0x18003a930  mov     rbx, [rdi+8]
0x18003a934  mov     rcx, [rbx]
0x18003a937  call    cs:__imp_GdipResetClip
0x18003a93d  test    eax, eax
0x18003a93f  jz      short loc_18003A944
0x18003a941  mov     [rbx+8], eax
0x18003a944  mov     rcx, rsi
0x18003a947  call    ?Reset@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@XZ; Gdiplus::GraphicsPath::Reset(void)
0x18003a94c  jmp     loc_18003A83F
0x18003a951  mov     [rdi+0E8h], r13
0x18003a958  jmp     loc_18003A846
0x18003a95d  mov     esi, 1
0x18003a962  cmp     [rcx+28h], r13b
0x18003a966  jz      loc_18003A9ED
0x18003a96c  cmp     [rcx+0CCh], r13d
0x18003a973  jle     short loc_18003A9ED
0x18003a975  lea     rcx, [rbp+pExceptionObject]
0x18003a979  mov     [rbp+pExceptionObject], r13
0x18003a97d  call    cs:__imp_GdipCreateRegion
0x18003a983  mov     r14, [rbp+pExceptionObject]
0x18003a987  mov     r15d, esi
0x18003a98a  mov     ebx, [rdi+0CCh]
0x18003a990  jmp     short loc_18003A9C6
0x18003a992  cmp     r15d, 5
0x18003a996  jge     short loc_18003A9CA
0x18003a998  mov     eax, 0CCCCCCCDh
0x18003a99d  mov     ecx, ebx
0x18003a99f  mul     ebx
0x18003a9a1  mov     r8d, 4
0x18003a9a7  shr     edx, 2
0x18003a9aa  lea     eax, [rdx+rdx*4]
0x18003a9ad  sub     ecx, eax
0x18003a9af  movsxd  rdx, ecx
0x18003a9b2  mov     rcx, r14
0x18003a9b5  add     rdx, rdx
0x18003a9b8  mov     rdx, [rdi+rdx*8+78h]
0x18003a9bd  call    cs:__imp_GdipCombineRegionPath
0x18003a9c3  add     r15d, esi
0x18003a9c6  sub     ebx, esi
0x18003a9c8  jns     short loc_18003A992
0x18003a9ca  mov     rbx, [rdi+8]
0x18003a9ce  xor     r8d, r8d
0x18003a9d1  mov     rdx, r14
0x18003a9d4  mov     rcx, [rbx]
0x18003a9d7  call    cs:__imp_GdipSetClipRegion
0x18003a9dd  test    eax, eax
0x18003a9df  jz      short loc_18003A9E4
0x18003a9e1  mov     [rbx+8], eax
0x18003a9e4  mov     rcx, r14
0x18003a9e7  call    cs:__imp_GdipDeleteRegion
0x18003a9ed  mov     ecx, [rdi+0CCh]
0x18003a9f3  mov     r14d, 66666667h
0x18003a9f9  mov     rbx, [rdi+8]
0x18003a9fd  mov     eax, r14d
0x18003aa00  imul    ecx
0x18003aa02  sar     edx, 1
0x18003aa04  mov     eax, edx
0x18003aa06  shr     eax, 1Fh
0x18003aa09  add     edx, eax
0x18003aa0b  lea     eax, [rdx+rdx*4]
0x18003aa0e  mov     rdx, [rdi+18h]
0x18003aa12  sub     ecx, eax
0x18003aa14  movsxd  r8, ecx
0x18003aa17  mov     rcx, [rbx]
0x18003aa1a  add     r8, r8
0x18003aa1d  mov     rdx, [rdx+8]
0x18003aa21  mov     r8, [rdi+r8*8+78h]
0x18003aa26  call    cs:__imp_GdipFillPath
0x18003aa2c  test    eax, eax
0x18003aa2e  jz      short loc_18003AA33
0x18003aa30  mov     [rbx+8], eax
0x18003aa33  cmp     [rdi+28h], r13b
0x18003aa37  jz      short loc_18003AA3F
0x18003aa39  add     [rdi+0CCh], esi
0x18003aa3f  mov     r8d, [rdi+0CCh]
0x18003aa46  mov     eax, r14d
0x18003aa49  imul    r8d
0x18003aa4c  sar     edx, 1
0x18003aa4e  mov     ecx, edx
0x18003aa50  shr     ecx, 1Fh
0x18003aa53  add     edx, ecx
0x18003aa55  lea     ecx, [rdx+rdx*4]
0x18003aa58  sub     r8d, ecx
0x18003aa5b  movsxd  rcx, r8d
0x18003aa5e  shl     rcx, 4
0x18003aa62  add     rcx, 78h ; 'x'
0x18003aa66  add     rcx, rdi
0x18003aa69  call    ?Reset@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@XZ; Gdiplus::GraphicsPath::Reset(void)
0x18003aa6e  mov     ecx, [rdi+0CCh]
0x18003aa74  mov     eax, r14d
0x18003aa77  imul    ecx
0x18003aa79  sar     edx, 1
0x18003aa7b  mov     eax, edx
0x18003aa7d  shr     eax, 1Fh
0x18003aa80  add     edx, eax
0x18003aa82  lea     eax, [rdx+rdx*4]
0x18003aa85  sub     ecx, eax
0x18003aa87  movsxd  rcx, ecx
0x18003aa8a  shl     rcx, 4
0x18003aa8e  add     rcx, 78h ; 'x'
0x18003aa92  add     rcx, rdi
0x18003aa95  call    ?SetFillMode@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@W4FillMode@2@@Z; Gdiplus::GraphicsPath::SetFillMode(Gdiplus::FillMode)
0x18003aa9a  jmp     loc_18003A846
0x18003aa9f  lea     rdx, _TI1J; pThrowInfo
0x18003aaa6  mov     dword ptr [rbp+pExceptionObject], 80004003h
0x18003aaad  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003aab1  call    _CxxThrowException_0
```
