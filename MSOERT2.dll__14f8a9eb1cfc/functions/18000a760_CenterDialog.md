# CenterDialog

- ea: `0x18000a760`
- end: `0x18000a8bc`
- name: `CenterDialog`
- size: `348`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a760`
- `0x180012fc0`

## import_xrefs

- `USER32!GetParent` at `0x18000a7ae`
- `USER32!GetParent` at `0x18000a7ae`
- `USER32!GetWindowRect` at `0x18000a7c0`
- `USER32!GetWindowRect` at `0x18000a7d8`
- `USER32!GetWindowRect` at `0x18000a7c0`
- `USER32!GetWindowRect` at `0x18000a7d8`
- `USER32!SetWindowPos` at `0x18000a899`
- `USER32!SetWindowPos` at `0x18000a899`
- `USER32!SystemParametersInfoA` at `0x18000a7a5`
- `USER32!SystemParametersInfoA` at `0x18000a7a5`
- `USER32!OffsetRect` at `0x18000a7f7`
- `USER32!OffsetRect` at `0x18000a80d`
- `USER32!OffsetRect` at `0x18000a823`
- `USER32!OffsetRect` at `0x18000a7f7`
- `USER32!OffsetRect` at `0x18000a80d`
- `USER32!OffsetRect` at `0x18000a823`

## pseudocode

```c
BOOL __fastcall CenterDialog(HWND hWnd)
{
  HWND Parent; // rax
  int left; // r10d
  int top; // r9d
  struct tagRECT rc; // [rsp+40h] [rbp+7h] BYREF
  struct tagRECT pvParam; // [rsp+50h] [rbp+17h] BYREF
  struct tagRECT v8; // [rsp+60h] [rbp+27h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp+37h] BYREF

  v8 = 0;
  rc = 0;
  Rect = 0;
  pvParam = 0;
  SystemParametersInfoA(0x30u, 0, &pvParam, 0);
  Parent = GetParent(hWnd);
  if ( Parent )
    GetWindowRect(Parent, &Rect);
  else
    Rect = pvParam;
  GetWindowRect(hWnd, &rc);
  v8 = Rect;
  OffsetRect(&rc, -rc.left, -rc.top);
  OffsetRect(&v8, -v8.left, -v8.top);
  OffsetRect(&v8, -rc.right, -rc.bottom);
  left = pvParam.right - rc.right;
  if ( pvParam.right - rc.right - (v8.right / 2 + Rect.left) >= 0 )
    left = v8.right / 2 + Rect.left;
  if ( left < pvParam.left )
    left = pvParam.left;
  top = pvParam.bottom - rc.bottom;
  if ( pvParam.bottom - rc.bottom - (v8.bottom / 2 + Rect.top) >= 0 )
    top = v8.bottom / 2 + Rect.top;
  if ( top < pvParam.top )
    top = pvParam.top;
  return SetWindowPos(hWnd, 0, left, top, 0, 0, 0x15u);
}

```

## disassembly

```asm
0x18000a760  mov     [rsp-8+arg_8], rbx
0x18000a765  push    rbp
0x18000a766  lea     rbp, [rsp-57h]
0x18000a76b  sub     rsp, 90h
0x18000a772  mov     rax, cs:__security_cookie
0x18000a779  xor     rax, rsp
0x18000a77c  mov     [rbp+57h+var_10], rax
0x18000a780  xorps   xmm0, xmm0
0x18000a783  lea     r8, [rbp+57h+pvParam]; pvParam
0x18000a787  xorps   xmm1, xmm1
0x18000a78a  xor     edx, edx; uiParam
0x18000a78c  mov     rbx, rcx
0x18000a78f  xor     r9d, r9d; fWinIni
0x18000a792  movups  xmmword ptr [rbp+57h+var_30.left], xmm0
0x18000a796  lea     ecx, [rdx+30h]; uiAction
0x18000a799  movups  xmmword ptr [rbp+57h+rc.left], xmm1
0x18000a79d  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18000a7a1  movups  [rbp+57h+pvParam], xmm1
0x18000a7a5  call    cs:__imp_SystemParametersInfoA
0x18000a7ab  mov     rcx, rbx; hWnd
0x18000a7ae  call    cs:__imp_GetParent
0x18000a7b4  test    rax, rax
0x18000a7b7  jz      short loc_18000A7C8
0x18000a7b9  lea     rdx, [rbp+57h+Rect]; lpRect
0x18000a7bd  mov     rcx, rax; hWnd
0x18000a7c0  call    cs:__imp_GetWindowRect
0x18000a7c6  jmp     short loc_18000A7D1
0x18000a7c8  movaps  xmm0, [rbp+57h+pvParam]
0x18000a7cc  movdqa  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18000a7d1  lea     rdx, [rbp+57h+rc]; lpRect
0x18000a7d5  mov     rcx, rbx; hWnd
0x18000a7d8  call    cs:__imp_GetWindowRect
0x18000a7de  mov     r8d, [rbp+57h+rc.top]
0x18000a7e2  lea     rcx, [rbp+57h+rc]; lprc
0x18000a7e6  mov     edx, [rbp+57h+rc.left]
0x18000a7e9  neg     r8d; dy
0x18000a7ec  movaps  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x18000a7f0  neg     edx; dx
0x18000a7f2  movdqa  xmmword ptr [rbp+57h+var_30.left], xmm0
0x18000a7f7  call    cs:__imp_OffsetRect
0x18000a7fd  mov     r8d, [rbp+57h+var_30.top]
0x18000a801  lea     rcx, [rbp+57h+var_30]; lprc
0x18000a805  mov     edx, [rbp+57h+var_30.left]
0x18000a808  neg     r8d; dy
0x18000a80b  neg     edx; dx
0x18000a80d  call    cs:__imp_OffsetRect
0x18000a813  mov     r8d, [rbp+57h+rc.bottom]
0x18000a817  lea     rcx, [rbp+57h+var_30]; lprc
0x18000a81b  mov     edx, [rbp+57h+rc.right]
0x18000a81e  neg     r8d; dy
0x18000a821  neg     edx; dx
0x18000a823  call    cs:__imp_OffsetRect
0x18000a829  mov     eax, [rbp+57h+var_30.right]
0x18000a82c  mov     r9d, 2
0x18000a832  mov     r8d, [rbp+57h+Rect.left]
0x18000a836  cdq
0x18000a837  mov     r10d, dword ptr [rbp+57h+pvParam+8]
0x18000a83b  mov     rcx, rbx; hWnd
0x18000a83e  sub     r10d, [rbp+57h+rc.right]
0x18000a842  idiv    r9d
0x18000a845  mov     [rsp+90h+uFlags], 15h; uFlags
0x18000a84d  add     r8d, eax
0x18000a850  mov     [rsp+90h+cy], 0; cy
0x18000a858  mov     eax, [rbp+57h+var_30.bottom]
0x18000a85b  cdq
0x18000a85c  mov     [rsp+90h+var_70], 0; cx
0x18000a864  idiv    r9d
0x18000a867  mov     edx, [rbp+57h+Rect.top]
0x18000a86a  mov     r9d, dword ptr [rbp+57h+pvParam+0Ch]
0x18000a86e  add     edx, eax
0x18000a870  cmp     r10d, r8d
0x18000a873  cmovns  r10d, r8d
0x18000a877  cmp     r10d, dword ptr [rbp+57h+pvParam]
0x18000a87b  cmovl   r10d, dword ptr [rbp+57h+pvParam]
0x18000a880  sub     r9d, [rbp+57h+rc.bottom]
0x18000a884  mov     r8d, r10d; X
0x18000a887  cmp     r9d, edx
0x18000a88a  cmovns  r9d, edx
0x18000a88e  cmp     r9d, dword ptr [rbp+57h+pvParam+4]
0x18000a892  cmovl   r9d, dword ptr [rbp+57h+pvParam+4]; Y
0x18000a897  xor     edx, edx; hWndInsertAfter
0x18000a899  call    cs:__imp_SetWindowPos
0x18000a89f  mov     rcx, [rbp+57h+var_10]
0x18000a8a3  xor     rcx, rsp; StackCookie
0x18000a8a6  call    __security_check_cookie
0x18000a8ab  mov     rbx, [rsp+90h+arg_8]
0x18000a8b3  add     rsp, 90h
0x18000a8ba  pop     rbp
0x18000a8bb  retn
```
