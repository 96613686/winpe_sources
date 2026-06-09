# CCanvas::SetPen(ulong,double,ulong,uchar,bool,bool)

- ea: `0x180099a84`
- end: `0x180099c2d`
- name: `?SetPen@CCanvas@@QEAAJKNKE_N0@Z`
- size: `425`
- prototype: `__int64 __usercall@<rax>(CCanvas *__hidden this@<rcx>, unsigned int iStyle@<edx>, double@<xmm2>, unsigned int@<r9d>, unsigned __int8, bool, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f0d0`
- `0x18003b548`
- `0x180089390`

## callees

- `0x1800240dc`
- `0x18002b894`
- `0x18002c59c`
- `0x180099a84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099ae5`
- `GDI32!CreatePen` at `0x180099ad3`
- `GDI32!CreatePen` at `0x180099ad3`
- `GDI32!SelectObject` at `0x180099b14`
- `GDI32!SelectObject` at `0x180099b14`
- `gdiplus!GdipSetPenLineJoin` at `0x180099be0`
- `gdiplus!GdipSetPenLineJoin` at `0x180099be0`
- `gdiplus!GdipSetPenEndCap` at `0x180099bb4`
- `gdiplus!GdipSetPenEndCap` at `0x180099bb4`
- `gdiplus!GdipSetPenStartCap` at `0x180099bca`
- `gdiplus!GdipSetPenStartCap` at `0x180099bca`
- `gdiplus!GdipCreatePen1` at `0x180099b8d`
- `gdiplus!GdipCreatePen1` at `0x180099b8d`
- `gdiplus!GdipAlloc` at `0x180099b3c`
- `gdiplus!GdipAlloc` at `0x180099b3c`

## pseudocode

```c
signed int __fastcall CCanvas::SetPen(HDC *this, int iStyle, double a3, COLORREF a4, unsigned __int8 a5, bool a6)
{
  int v9; // edx
  HPEN Pen; // rax
  signed int result; // eax
  HDC v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdi
  int v15; // eax
  HDC v16; // rdi
  int started; // eax
  HDC v18; // rdi
  int v19; // eax

  CCanvas::ResetPen((CCanvas *)this);
  if ( !*((_DWORD *)this + 61) )
  {
    if ( this[1] )
    {
      v13 = GdipAlloc(16);
      v14 = v13;
      if ( v13 )
      {
        *(_QWORD *)v13 = 0;
        *(_DWORD *)(v13 + 8) = GdipCreatePen1(
                                 BYTE2(a4) | a4 & 0xFF00 | (((unsigned __int8)a4 | ((unsigned __int8)~a5 << 8)) << 16),
                                 (unsigned __int8)a4,
                                 0,
                                 v13);
      }
      else
      {
        v14 = 0;
      }
      this[2] = (HDC)v14;
      if ( !v14 )
        return -2147024882;
      v15 = GdipSetPenEndCap(*(_QWORD *)v14, 2);
      if ( v15 )
        *(_DWORD *)(v14 + 8) = v15;
      v16 = this[2];
      started = GdipSetPenStartCap(*(_QWORD *)v16, 2);
      if ( started )
        *((_DWORD *)v16 + 2) = started;
      v18 = this[2];
      v19 = GdipSetPenLineJoin(*(_QWORD *)v18, 2);
      if ( v19 )
        *((_DWORD *)v18 + 2) = v19;
      *((_DWORD *)this + 8) = Gdiplus::Graphics::GetSmoothingMode(this[1]);
      *((_DWORD *)this + 9) = 4 * a6;
      CCanvas::SetSmoothingMode((CCanvas *)this);
      *((_BYTE *)this + 200) = a5;
      *((_BYTE *)this + 208) = 0;
      return 0;
    }
    return -2147467261;
  }
  if ( !this[31] )
    return -2147467261;
  *((_DWORD *)this + 80) = a4;
  v9 = (int)(a3 + 0.5);
  *((_DWORD *)this + 78) = v9;
  Pen = CreatePen(iStyle, v9, a4);
  this[34] = (HDC)Pen;
  if ( Pen )
  {
    v12 = this[31];
    *((_DWORD *)this + 77) = 1;
    this[33] = (HDC)SelectObject(v12, Pen);
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180099a84  push    rbx
0x180099a86  push    rbp
0x180099a87  push    rsi
0x180099a88  push    rdi
0x180099a89  sub     rsp, 38h
0x180099a8d  movaps  [rsp+58h+var_38], xmm6
0x180099a92  mov     esi, r9d
0x180099a95  movaps  xmm6, xmm2
0x180099a98  mov     edi, edx
0x180099a9a  mov     rbx, rcx
0x180099a9d  call    ?ResetPen@CCanvas@@QEAAXXZ; CCanvas::ResetPen(void)
0x180099aa2  cmp     dword ptr [rbx+0F4h], 0
0x180099aa9  jz      short loc_180099B26
0x180099aab  cmp     qword ptr [rbx+0F8h], 0
0x180099ab3  jz      short loc_180099B2D
0x180099ab5  addsd   xmm6, cs:__real@3fe0000000000000
0x180099abd  mov     r8d, esi; color
0x180099ac0  mov     [rbx+140h], esi
0x180099ac6  mov     ecx, edi; iStyle
0x180099ac8  cvttsd2si rdx, xmm6; cWidth
0x180099acd  mov     [rbx+138h], edx
0x180099ad3  call    cs:__imp_CreatePen
0x180099ad9  mov     [rbx+110h], rax
0x180099ae0  test    rax, rax
0x180099ae3  jnz     short loc_180099B00
0x180099ae5  call    cs:__imp_GetLastError
0x180099aeb  test    eax, eax
0x180099aed  jle     loc_180099C1F
0x180099af3  movzx   eax, ax
0x180099af6  or      eax, 80070000h
0x180099afb  jmp     loc_180099C1F
0x180099b00  mov     rcx, [rbx+0F8h]; hdc
0x180099b07  mov     rdx, rax; h
0x180099b0a  mov     dword ptr [rbx+134h], 1
0x180099b14  call    cs:__imp_SelectObject
0x180099b1a  mov     [rbx+108h], rax
0x180099b21  jmp     loc_180099C1D
0x180099b26  cmp     qword ptr [rbx+8], 0
0x180099b2b  jnz     short loc_180099B37
0x180099b2d  mov     eax, 80004003h
0x180099b32  jmp     loc_180099C1F
0x180099b37  mov     ecx, 10h
0x180099b3c  call    cs:__imp_GdipAlloc
0x180099b42  mov     bpl, [rsp+58h+arg_20]
0x180099b4a  mov     rdi, rax
0x180099b4d  test    rax, rax
0x180099b50  jz      short loc_180099B98
0x180099b52  mov     qword ptr [rax], 0
0x180099b59  mov     cl, bpl
0x180099b5c  not     cl
0x180099b5e  movzx   edx, sil
0x180099b62  movzx   ecx, cl
0x180099b65  xorps   xmm1, xmm1
0x180099b68  shl     ecx, 8
0x180099b6b  mov     r9, rdi
0x180099b6e  or      ecx, edx
0x180099b70  movzx   eax, si
0x180099b73  shl     ecx, 10h
0x180099b76  and     eax, 0FFFFFF00h
0x180099b7b  or      ecx, eax
0x180099b7d  shr     esi, 10h
0x180099b80  movzx   eax, sil
0x180099b84  xor     r8d, r8d
0x180099b87  cvtsd2ss xmm1, xmm6
0x180099b8b  or      ecx, eax
0x180099b8d  call    cs:__imp_GdipCreatePen1
0x180099b93  mov     [rdi+8], eax
0x180099b96  jmp     short loc_180099B9A
0x180099b98  xor     edi, edi
0x180099b9a  mov     [rbx+10h], rdi
0x180099b9e  test    rdi, rdi
0x180099ba1  jnz     short loc_180099BAA
0x180099ba3  mov     eax, 8007000Eh
0x180099ba8  jmp     short loc_180099C1F
0x180099baa  mov     rcx, [rdi]
0x180099bad  mov     esi, 2
0x180099bb2  mov     edx, esi
0x180099bb4  call    cs:__imp_GdipSetPenEndCap
0x180099bba  test    eax, eax
0x180099bbc  jz      short loc_180099BC1
0x180099bbe  mov     [rdi+8], eax
0x180099bc1  mov     rdi, [rbx+10h]
0x180099bc5  mov     edx, esi
0x180099bc7  mov     rcx, [rdi]
0x180099bca  call    cs:__imp_GdipSetPenStartCap
0x180099bd0  test    eax, eax
0x180099bd2  jz      short loc_180099BD7
0x180099bd4  mov     [rdi+8], eax
0x180099bd7  mov     rdi, [rbx+10h]
0x180099bdb  mov     edx, esi
0x180099bdd  mov     rcx, [rdi]
0x180099be0  call    cs:__imp_GdipSetPenLineJoin
0x180099be6  test    eax, eax
0x180099be8  jz      short loc_180099BED
0x180099bea  mov     [rdi+8], eax
0x180099bed  mov     rcx, [rbx+8]
0x180099bf1  call    ?GetSmoothingMode@Graphics@Gdiplus@@QEBA?AW4SmoothingMode@2@XZ; Gdiplus::Graphics::GetSmoothingMode(void)
0x180099bf6  mov     [rbx+20h], eax
0x180099bf9  mov     rcx, rbx; this
0x180099bfc  movzx   eax, [rsp+58h+arg_28]
0x180099c04  shl     eax, 2
0x180099c07  mov     [rbx+24h], eax
0x180099c0a  call    ?SetSmoothingMode@CCanvas@@IEAAXXZ; CCanvas::SetSmoothingMode(void)
0x180099c0f  mov     [rbx+0C8h], bpl
0x180099c16  mov     byte ptr [rbx+0D0h], 0
0x180099c1d  xor     eax, eax
0x180099c1f  movaps  xmm6, [rsp+58h+var_38]
0x180099c24  add     rsp, 38h
0x180099c28  pop     rdi
0x180099c29  pop     rsi
0x180099c2a  pop     rbp
0x180099c2b  pop     rbx
0x180099c2c  retn
```
