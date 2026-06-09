# WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawGhostBar(void)

- ea: `0x180022558`
- end: `0x1800226ad`
- name: `?DrawGhostBar@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAXXZ`
- size: `341`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800249a0`
- `0x180027544`

## callees

- `0x180001800`
- `0x180022558`

## import_xrefs

- `GDI32!PatBlt` at `0x180022668`
- `GDI32!PatBlt` at `0x180022668`
- `GDI32!SelectObject` at `0x180022630`
- `GDI32!SelectObject` at `0x180022674`
- `GDI32!SelectObject` at `0x180022630`
- `GDI32!SelectObject` at `0x180022674`
- `GDI32!DeleteObject` at `0x18002261d`
- `GDI32!DeleteObject` at `0x18002267d`
- `GDI32!DeleteObject` at `0x18002261d`
- `GDI32!DeleteObject` at `0x18002267d`
- `GDI32!CreateBitmap` at `0x180022600`
- `GDI32!CreateBitmap` at `0x180022600`
- `GDI32!CreatePatternBrush` at `0x180022611`
- `GDI32!CreatePatternBrush` at `0x180022611`
- `USER32!ReleaseDC` at `0x180022689`
- `USER32!ReleaseDC` at `0x180022689`
- `USER32!GetWindowDC` at `0x1800225c1`
- `USER32!GetWindowDC` at `0x1800225c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawGhostBar(_DWORD *a1)
{
  int v1; // esi
  int v2; // edi
  int v3; // r13d
  int v4; // r15d
  __int64 v5; // rax
  HWND v6; // r12
  HDC WindowDC; // rax
  __int64 v8; // r10
  HDC v9; // rbp
  HBITMAP Bitmap; // rax
  HBITMAP v11; // rbx
  HBRUSH PatternBrush; // r14
  HGDIOBJ v13; // rbx
  int v14; // [rsp+30h] [rbp-78h]
  int x; // [rsp+38h] [rbp-70h]
  _WORD Bits[8]; // [rsp+40h] [rbp-68h] BYREF

  if ( a1[18] == -1 )
  {
    v1 = a1[8];
    if ( v1 != -1 )
    {
      v2 = a1[5];
      v3 = a1[6];
      v4 = a1[10];
      x = a1[4];
      v14 = a1[12];
      v5 = (__int64)(a1 - 16);
      if ( !a1 )
        v5 = 8;
      v6 = *(HWND *)v5;
      WindowDC = GetWindowDC(*(HWND *)v5);
      v8 = 0;
      v9 = WindowDC;
      do
      {
        Bits[v8] = 21845 << (v8 & 1);
        v8 = (unsigned int)(v8 + 1);
      }
      while ( (int)v8 < 8 );
      Bitmap = CreateBitmap(8, 8, 1u, 1u, Bits);
      v11 = Bitmap;
      if ( Bitmap )
      {
        PatternBrush = CreatePatternBrush(Bitmap);
        DeleteObject(v11);
        if ( PatternBrush )
        {
          v13 = SelectObject(v9, PatternBrush);
          PatBlt(v9, x, v1 + v2, v3 - x, v14 + v4, 0x5A0049u);
          SelectObject(v9, v13);
          DeleteObject(PatternBrush);
        }
      }
      ReleaseDC(v6, v9);
    }
  }
}

```

## disassembly

```asm
0x180022558  push    rbx
0x18002255a  push    rbp
0x18002255b  push    rsi
0x18002255c  push    rdi
0x18002255d  push    r12
0x18002255f  push    r13
0x180022561  push    r14
0x180022563  push    r15
0x180022565  sub     rsp, 68h
0x180022569  mov     rax, cs:__security_cookie
0x180022570  xor     rax, rsp
0x180022573  mov     [rsp+0A8h+var_58], rax
0x180022578  cmp     dword ptr [rcx+48h], 0FFFFFFFFh
0x18002257c  jnz     loc_18002268F
0x180022582  mov     esi, [rcx+20h]
0x180022585  cmp     esi, 0FFFFFFFFh
0x180022588  jz      loc_18002268F
0x18002258e  mov     eax, [rcx+10h]
0x180022591  test    rcx, rcx
0x180022594  mov     edi, [rcx+14h]
0x180022597  mov     ebx, 8
0x18002259c  mov     r13d, [rcx+18h]
0x1800225a0  mov     r15d, [rcx+28h]
0x1800225a4  mov     [rsp+0A8h+x], eax
0x1800225a8  mov     eax, [rcx+30h]
0x1800225ab  mov     [rsp+0A8h+var_78], eax
0x1800225af  lea     rax, [rcx-40h]
0x1800225b3  cmovz   rax, rbx
0x1800225b7  mov     [rsp+0A8h+var_74], edi
0x1800225bb  mov     r12, [rax]
0x1800225be  mov     rcx, r12; hWnd
0x1800225c1  call    cs:__imp_GetWindowDC
0x1800225c7  xor     r10d, r10d
0x1800225ca  lea     r8d, [rbx-7]; nPlanes
0x1800225ce  mov     rbp, rax
0x1800225d1  mov     ecx, r10d
0x1800225d4  mov     r9d, 5555h
0x1800225da  and     ecx, r8d
0x1800225dd  shl     r9w, cl
0x1800225e1  mov     [rsp+r10*2+0A8h+Bits], r9w
0x1800225e7  add     r10d, r8d
0x1800225ea  cmp     r10d, ebx
0x1800225ed  jl      short loc_1800225D1
0x1800225ef  lea     rax, [rsp+0A8h+Bits]
0x1800225f4  mov     r9d, r8d; nBitCount
0x1800225f7  mov     edx, ebx; nHeight
0x1800225f9  mov     [rsp+0A8h+lpBits], rax; lpBits
0x1800225fe  mov     ecx, ebx; nWidth
0x180022600  call    cs:__imp_CreateBitmap
0x180022606  mov     rbx, rax
0x180022609  test    rax, rax
0x18002260c  jz      short loc_180022683
0x18002260e  mov     rcx, rax; hbm
0x180022611  call    cs:__imp_CreatePatternBrush
0x180022617  mov     rcx, rbx; ho
0x18002261a  mov     r14, rax
0x18002261d  call    cs:__imp_DeleteObject
0x180022623  test    r14, r14
0x180022626  jz      short loc_180022683
0x180022628  mov     rdx, r14; h
0x18002262b  mov     rcx, rbp; hdc
0x18002262e  add     edi, esi
0x180022630  call    cs:__imp_SelectObject
0x180022636  sub     r13d, [rsp+0A8h+x]
0x18002263b  sub     r15d, edi
0x18002263e  add     r15d, [rsp+0A8h+var_78]
0x180022643  mov     r9d, r13d; w
0x180022646  add     r15d, [rsp+0A8h+var_74]
0x18002264b  mov     r8d, edi; y
0x18002264e  mov     edx, [rsp+0A8h+x]; x
0x180022652  add     r15d, esi
0x180022655  mov     [rsp+0A8h+rop], 5A0049h; rop
0x18002265d  mov     rcx, rbp; hdc
0x180022660  mov     dword ptr [rsp+0A8h+lpBits], r15d; h
0x180022665  mov     rbx, rax
0x180022668  call    cs:__imp_PatBlt
0x18002266e  mov     rdx, rbx; h
0x180022671  mov     rcx, rbp; hdc
0x180022674  call    cs:__imp_SelectObject
0x18002267a  mov     rcx, r14; ho
0x18002267d  call    cs:__imp_DeleteObject
0x180022683  mov     rdx, rbp; hDC
0x180022686  mov     rcx, r12; hWnd
0x180022689  call    cs:__imp_ReleaseDC
0x18002268f  mov     rcx, [rsp+0A8h+var_58]
0x180022694  xor     rcx, rsp; StackCookie
0x180022697  call    __security_check_cookie
0x18002269c  add     rsp, 68h
0x1800226a0  pop     r15
0x1800226a2  pop     r14
0x1800226a4  pop     r13
0x1800226a6  pop     r12
0x1800226a8  pop     rdi
0x1800226a9  pop     rsi
0x1800226aa  pop     rbp
0x1800226ab  pop     rbx
0x1800226ac  retn
```
