# FrameWindow::OnPaint(WTL::CDCT<0>)

- ea: `0x180025440`
- end: `0x1800255e8`
- name: `?OnPaint@FrameWindow@@QEAAXV?$CDCT@$0A@@WTL@@@Z`
- size: `424`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b910`

## callees

- `0x180001800`
- `0x180002678`
- `0x180025440`

## import_xrefs

- `GDI32!DeleteDC` at `0x1800255ca`
- `GDI32!DeleteDC` at `0x1800255ca`
- `USER32!GetDC` at `0x180025509`
- `USER32!GetDC` at `0x180025509`
- `USER32!GetClientRect` at `0x180025489`
- `USER32!GetClientRect` at `0x180025489`
- `USER32!FillRect` at `0x180025551`
- `USER32!FillRect` at `0x180025565`
- `USER32!FillRect` at `0x18002557e`
- `USER32!FillRect` at `0x18002558e`
- `USER32!FillRect` at `0x18002559e`
- `USER32!FillRect` at `0x1800255ae`
- `USER32!FillRect` at `0x180025551`
- `USER32!FillRect` at `0x180025565`
- `USER32!FillRect` at `0x18002557e`
- `USER32!FillRect` at `0x18002558e`
- `USER32!FillRect` at `0x18002559e`
- `USER32!FillRect` at `0x1800255ae`
- `USER32!EndPaint` at `0x1800255bc`
- `USER32!EndPaint` at `0x1800255bc`
- `USER32!BeginPaint` at `0x180025540`
- `USER32!BeginPaint` at `0x180025540`
- `USER32!InflateRect` at `0x1800254e6`
- `USER32!InflateRect` at `0x1800254e6`

## pseudocode

```c
BOOL __fastcall FrameWindow::OnPaint(__int64 a1)
{
  char v1; // al
  int v2; // ebx
  int v4; // esi
  unsigned __int64 v5; // xmm0_8
  HWND v6; // rcx
  HDC DC; // rbx
  HBRUSH v8; // rsi
  BOOL result; // eax
  struct tagRECT Rect; // [rsp+20h] [rbp-99h] BYREF
  RECT rc; // [rsp+30h] [rbp-89h] BYREF
  RECT v12; // [rsp+40h] [rbp-79h] BYREF
  RECT v13; // [rsp+50h] [rbp-69h] BYREF
  RECT v14; // [rsp+60h] [rbp-59h] BYREF
  RECT v15; // [rsp+70h] [rbp-49h] BYREF
  RECT v16; // [rsp+80h] [rbp-39h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+90h] [rbp-29h] BYREF

  v1 = *(_BYTE *)(a1 + 435);
  v2 = *(_DWORD *)(a1 + 648);
  v4 = v1 == 0;
  if ( v1 )
    v2 -= *(_DWORD *)(a1 + 644);
  GetClientRect(*(HWND *)(a1 + 8), &Rect);
  v13 = Rect;
  v16 = Rect;
  v5 = _mm_srli_si128((__m128i)Rect, 8).m128i_u64[0];
  v14 = Rect;
  v15 = Rect;
  v13.right = v4 + Rect.left;
  v16.top = HIDWORD(v5) - v4;
  v14.bottom = v4 + Rect.top;
  v15.left = v5 - v4;
  InflateRect(&Rect, -v4, -v4);
  v6 = *(HWND *)(a1 + 8);
  rc = Rect;
  v12 = Rect;
  rc.bottom = v4 + v2;
  v12.top = v4 + v2;
  DC = GetDC(v6);
  v8 = *(HBRUSH *)((-(__int64)(*(_BYTE *)(a1 + 688) != 0) & 0xFFFFFFFFFFFFFFF8uLL) + a1 + 272);
  memset_0(&Paint, 0, sizeof(Paint));
  BeginPaint(*(HWND *)(a1 + 8), &Paint);
  FillRect(DC, &rc, v8);
  FillRect(DC, &v12, *(HBRUSH *)(a1 + 256));
  if ( !*(_BYTE *)(a1 + 435) )
  {
    FillRect(DC, &v13, v8);
    FillRect(DC, &v14, v8);
    FillRect(DC, &v15, v8);
    FillRect(DC, &v16, v8);
  }
  result = EndPaint(*(HWND *)(a1 + 8), &Paint);
  if ( DC )
    return DeleteDC(DC);
  return result;
}

```

## disassembly

```asm
0x180025440  push    rbp
0x180025442  push    rbx
0x180025443  push    rsi
0x180025444  push    rdi
0x180025445  lea     rbp, [rsp-3Fh]
0x18002544a  sub     rsp, 0F8h
0x180025451  mov     rax, cs:__security_cookie
0x180025458  xor     rax, rsp
0x18002545b  mov     [rbp+57h+var_30], rax
0x18002545f  mov     al, [rcx+1B3h]
0x180025465  xor     esi, esi
0x180025467  mov     ebx, [rcx+288h]
0x18002546d  test    al, al
0x18002546f  mov     rdi, rcx
0x180025472  setz    sil
0x180025476  test    al, al
0x180025478  jz      short loc_180025480
0x18002547a  sub     ebx, [rcx+284h]
0x180025480  mov     rcx, [rcx+8]; hWnd
0x180025484  lea     rdx, [rsp+110h+Rect]; lpRect
0x180025489  call    cs:__imp_GetClientRect
0x18002548f  movaps  xmm1, xmmword ptr [rsp+110h+Rect.left]
0x180025494  movq    rcx, xmm1
0x180025499  movdqa  xmmword ptr [rbp+57h+var_C0.left], xmm1
0x18002549e  movdqa  xmm0, xmm1
0x1800254a2  movdqa  xmmword ptr [rbp+57h+var_90.left], xmm1
0x1800254a7  psrldq  xmm0, 8
0x1800254ac  movq    rdx, xmm0
0x1800254b1  movdqa  xmmword ptr [rbp+57h+var_B0.left], xmm1
0x1800254b6  lea     eax, [rsi+rcx]
0x1800254b9  movdqa  xmmword ptr [rbp+57h+var_A0.left], xmm1
0x1800254be  mov     [rbp+57h+var_C0.right], eax
0x1800254c1  mov     eax, edx
0x1800254c3  shr     rdx, 20h
0x1800254c7  sub     eax, esi
0x1800254c9  sub     edx, esi
0x1800254cb  shr     rcx, 20h
0x1800254cf  mov     [rbp+57h+var_90.top], edx
0x1800254d2  add     ecx, esi
0x1800254d4  mov     edx, esi
0x1800254d6  mov     [rbp+57h+var_B0.bottom], ecx
0x1800254d9  neg     edx; dx
0x1800254db  mov     [rbp+57h+var_A0.left], eax
0x1800254de  mov     r8d, edx; dy
0x1800254e1  lea     rcx, [rsp+110h+Rect]; lprc
0x1800254e6  call    cs:__imp_InflateRect
0x1800254ec  movaps  xmm0, xmmword ptr [rsp+110h+Rect.left]
0x1800254f1  lea     eax, [rsi+rbx]
0x1800254f4  mov     rcx, [rdi+8]; hWnd
0x1800254f8  movdqa  xmmword ptr [rsp+110h+rc.left], xmm0
0x1800254fe  movdqa  xmmword ptr [rbp+57h+var_D0.left], xmm0
0x180025503  mov     [rbp+57h+rc.bottom], eax
0x180025506  mov     [rbp+57h+var_D0.top], eax
0x180025509  call    cs:__imp_GetDC
0x18002550f  mov     rbx, rax
0x180025512  mov     al, [rdi+2B0h]
0x180025518  neg     al
0x18002551a  sbb     rcx, rcx
0x18002551d  xor     edx, edx; Val
0x18002551f  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180025523  lea     r8d, [rdx+48h]; Size
0x180025527  mov     rsi, [rcx+rdi+110h]
0x18002552f  lea     rcx, [rbp+57h+Paint]; void *
0x180025533  call    memset_0
0x180025538  mov     rcx, [rdi+8]; hWnd
0x18002553c  lea     rdx, [rbp+57h+Paint]; lpPaint
0x180025540  call    cs:__imp_BeginPaint
0x180025546  mov     r8, rsi; hbr
0x180025549  lea     rdx, [rsp+110h+rc]; lprc
0x18002554e  mov     rcx, rbx; hDC
0x180025551  call    cs:__imp_FillRect
0x180025557  mov     r8, [rdi+100h]; hbr
0x18002555e  lea     rdx, [rbp+57h+var_D0]; lprc
0x180025562  mov     rcx, rbx; hDC
0x180025565  call    cs:__imp_FillRect
0x18002556b  cmp     byte ptr [rdi+1B3h], 0
0x180025572  jnz     short loc_1800255B4
0x180025574  mov     r8, rsi; hbr
0x180025577  lea     rdx, [rbp+57h+var_C0]; lprc
0x18002557b  mov     rcx, rbx; hDC
0x18002557e  call    cs:__imp_FillRect
0x180025584  mov     r8, rsi; hbr
0x180025587  lea     rdx, [rbp+57h+var_B0]; lprc
0x18002558b  mov     rcx, rbx; hDC
0x18002558e  call    cs:__imp_FillRect
0x180025594  mov     r8, rsi; hbr
0x180025597  lea     rdx, [rbp+57h+var_A0]; lprc
0x18002559b  mov     rcx, rbx; hDC
0x18002559e  call    cs:__imp_FillRect
0x1800255a4  mov     r8, rsi; hbr
0x1800255a7  lea     rdx, [rbp+57h+var_90]; lprc
0x1800255ab  mov     rcx, rbx; hDC
0x1800255ae  call    cs:__imp_FillRect
0x1800255b4  mov     rcx, [rdi+8]; hWnd
0x1800255b8  lea     rdx, [rbp+57h+Paint]; lpPaint
0x1800255bc  call    cs:__imp_EndPaint
0x1800255c2  test    rbx, rbx
0x1800255c5  jz      short loc_1800255D0
0x1800255c7  mov     rcx, rbx; hdc
0x1800255ca  call    cs:__imp_DeleteDC
0x1800255d0  mov     rcx, [rbp+57h+var_30]
0x1800255d4  xor     rcx, rsp; StackCookie
0x1800255d7  call    __security_check_cookie
0x1800255dc  add     rsp, 0F8h
0x1800255e3  pop     rdi
0x1800255e4  pop     rsi
0x1800255e5  pop     rbx
0x1800255e6  pop     rbp
0x1800255e7  retn
```
