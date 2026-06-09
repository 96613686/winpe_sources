# GdipUtil::BufferedPainterBase::MirrorRegion(HDC__ *,HRGN__ * *)

- ea: `0x18002586c`
- end: `0x180025981`
- name: `?MirrorRegion@BufferedPainterBase@GdipUtil@@KAXPEAUHDC__@@PEAPEAUHRGN__@@@Z`
- size: `277`
- prototype: `void __fastcall(HDC, HRGN *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a160`

## callees

- `0x18002586c`
- `0x18003f800`

## import_xrefs

- `USER32!WindowFromDC` at `0x18002588d`
- `USER32!WindowFromDC` at `0x18002588d`
- `USER32!GetClientRect` at `0x1800258b4`
- `USER32!GetClientRect` at `0x1800258b4`
- `GDI32!GetRegionData` at `0x1800258ca`
- `GDI32!GetRegionData` at `0x1800258f4`
- `GDI32!GetRegionData` at `0x1800258ca`
- `GDI32!GetRegionData` at `0x1800258f4`
- `GDI32!ExtCreateRegion` at `0x18002592c`
- `GDI32!ExtCreateRegion` at `0x18002592c`
- `GDI32!DeleteObject` at `0x18002593d`
- `GDI32!DeleteObject` at `0x18002593d`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18002594e`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18002594e`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x1800258de`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x1800258de`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002589d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002589d`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180025973`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002597a`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180025973`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002597a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GdipUtil::BufferedPainterBase::MirrorRegion(HDC a1, HRGN *a2)
{
  HWND v3; // rax
  int v4; // edx
  Base *v5; // rcx
  DWORD RegionData; // eax
  unsigned __int64 v7; // rdx
  bool v8; // r8
  DWORD v9; // esi
  RGNDATA *v10; // rbx
  Base *v11; // rcx
  HRGN v12; // rsi
  void *v13; // rdx
  struct tagRECT Rect; // [rsp+28h] [rbp-40h] BYREF
  XFORM x; // [rsp+38h] [rbp-30h] BYREF

  v3 = WindowFromDC(a1);
  if ( !v3 )
  {
    Base::Throw((Base *)0x80070057LL, v4);
    __debugbreak();
  }
  Rect = 0;
  if ( !GetClientRect(v3, &Rect) || (RegionData = GetRegionData(*a2, 0, 0), (v9 = RegionData) == 0) )
  {
LABEL_11:
    Base::ThrowLastError(v5);
    JUMPOUT(0x180025980LL);
  }
  LOBYTE(v7) = 1;
  v10 = (RGNDATA *)BasePrivate::New((BasePrivate *)RegionData, v7, v8);
  if ( GetRegionData(*a2, v9, v10) != v9
    || (*(__m128i *)&x.eM11 = _mm_load_si128((const __m128i *)&_xmm),
        x.eDx = (float)Rect.right,
        x.eDy = 0.0,
        (v12 = ExtCreateRegion(&x, v9, v10)) == 0) )
  {
    Base::ThrowLastError(v11);
    goto LABEL_11;
  }
  DeleteObject(*a2);
  *a2 = v12;
  if ( v10 )
    BasePrivate::Delete((BasePrivate *)v10, v13);
}

```

## disassembly

```asm
0x18002586c  mov     [rsp+arg_10], rbx
0x180025871  mov     [rsp+arg_18], rsi
0x180025876  push    rdi
0x180025877  sub     rsp, 60h
0x18002587b  mov     rax, cs:__security_cookie
0x180025882  xor     rax, rsp
0x180025885  mov     [rsp+68h+var_18], rax
0x18002588a  mov     rdi, rdx
0x18002588d  call    cs:__imp_WindowFromDC
0x180025893  test    rax, rax
0x180025896  jnz     short loc_1800258A4
0x180025898  mov     ecx, 80070057h
0x18002589d  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x1800258a3  int     3; Trap to Debugger
0x1800258a4  xorps   xmm0, xmm0
0x1800258a7  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x1800258ac  lea     rdx, [rsp+68h+Rect]; lpRect
0x1800258b1  mov     rcx, rax; hWnd
0x1800258b4  call    cs:__imp_GetClientRect
0x1800258ba  test    eax, eax
0x1800258bc  jz      loc_18002597A
0x1800258c2  xor     r8d, r8d; lpRgnData
0x1800258c5  xor     edx, edx; nCount
0x1800258c7  mov     rcx, [rdi]; hrgn
0x1800258ca  call    cs:__imp_GetRegionData
0x1800258d0  mov     esi, eax
0x1800258d2  test    eax, eax
0x1800258d4  jz      loc_18002597A
0x1800258da  mov     ecx, esi
0x1800258dc  mov     dl, 1
0x1800258de  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x1800258e4  mov     rbx, rax
0x1800258e7  mov     [rsp+68h+var_48], rax
0x1800258ec  mov     r8, rax; lpRgnData
0x1800258ef  mov     edx, esi; nCount
0x1800258f1  mov     rcx, [rdi]; hrgn
0x1800258f4  call    cs:__imp_GetRegionData
0x1800258fa  cmp     eax, esi
0x1800258fc  jnz     short loc_180025973
0x1800258fe  movdqa  xmm0, cs:__xmm@3f8000000000000000000000bf800000
0x180025906  movups  xmmword ptr [rsp+68h+x.eM11], xmm0
0x18002590b  movd    xmm0, [rsp+68h+Rect.right]
0x180025911  cvtdq2ps xmm0, xmm0
0x180025914  movss   [rsp+68h+x.eDx], xmm0
0x18002591a  mov     [rsp+68h+x.eDy], 0
0x180025922  mov     r8, rbx; lpData
0x180025925  mov     edx, esi; nCount
0x180025927  lea     rcx, [rsp+68h+x]; lpx
0x18002592c  call    cs:__imp_ExtCreateRegion
0x180025932  mov     rsi, rax
0x180025935  test    rax, rax
0x180025938  jz      short loc_180025973
0x18002593a  mov     rcx, [rdi]; ho
0x18002593d  call    cs:__imp_DeleteObject
0x180025943  mov     [rdi], rsi
0x180025946  test    rbx, rbx
0x180025949  jz      short loc_180025954
0x18002594b  mov     rcx, rbx
0x18002594e  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x180025954  mov     rcx, [rsp+68h+var_18]
0x180025959  xor     rcx, rsp; StackCookie
0x18002595c  call    __security_check_cookie
0x180025961  lea     r11, [rsp+68h+var_8]
0x180025966  mov     rbx, [r11+20h]
0x18002596a  mov     rsi, [r11+28h]
0x18002596e  mov     rsp, r11
0x180025971  pop     rdi
0x180025972  retn
0x180025973  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x180025979  nop
0x18002597a  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
```
