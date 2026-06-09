# CInkOverlay::_InvalidateWindow(tagRECT *,HRGN__ *,int,int)

- ea: `0x1800e0ab0`
- end: `0x1800e0c15`
- name: `?_InvalidateWindow@CInkOverlay@@AEAAHPEAUtagRECT@@PEAUHRGN__@@HH@Z`
- size: `357`
- prototype: `int(CInkOverlay *__hidden this, struct tagRECT *, HRGN, int, int)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ca60`
- `0x180036504`
- `0x1800d8c30`
- `0x1800dc3d8`
- `0x1800dfb30`
- `0x1800e1434`
- `0x1800e1d70`
- `0x1800e20b0`
- `0x1800e4650`

## callees

- `0x1800c9fac`
- `0x1800e0ab0`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e0b7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e0b7f`
- `USER32!IsRectEmpty` at `0x1800e0b09`
- `USER32!IsRectEmpty` at `0x1800e0b09`
- `USER32!CopyRect` at `0x1800e0aee`
- `USER32!CopyRect` at `0x1800e0aee`
- `USER32!RedrawWindow` at `0x1800e0bc1`
- `USER32!RedrawWindow` at `0x1800e0bc1`
- `USER32!GetWindowThreadProcessId` at `0x1800e0b8d`
- `USER32!GetWindowThreadProcessId` at `0x1800e0b8d`
- `USER32!IntersectRect` at `0x1800e0b71`
- `USER32!IntersectRect` at `0x1800e0b71`
- `GDI32!CombineRgn` at `0x1800e0b4e`
- `GDI32!CombineRgn` at `0x1800e0b4e`
- `GDI32!CreateRectRgn` at `0x1800e0b2f`
- `GDI32!CreateRectRgn` at `0x1800e0b2f`
- `GDI32!DeleteObject` at `0x1800e0bf1`
- `GDI32!DeleteObject` at `0x1800e0bf1`

## pseudocode

```c
__int64 __fastcall CInkOverlay::_InvalidateWindow(CInkOverlay *this, struct tagRECT *a2, HRGN a3, int a4, int a5)
{
  struct tagRECT *p_rcDst; // rbp
  HRGN RectRgn; // rax
  HRGN v11; // rdi
  DWORD CurrentThreadId; // ebx
  DWORD WindowThreadProcessId; // eax
  int v14; // edx
  UINT v15; // edx
  int v16; // eax
  unsigned int v17; // ebx
  struct tagRECT rcDst; // [rsp+30h] [rbp-58h] BYREF

  rcDst = 0;
  CopyRect(&rcDst, (const RECT *)this + 21);
  if ( !a5 || IsRectEmpty(&rcDst) )
  {
    v11 = a3;
    p_rcDst = a2;
  }
  else
  {
    p_rcDst = &rcDst;
    if ( a3 )
    {
      RectRgn = CreateRectRgn(rcDst.left, rcDst.top, rcDst.right, rcDst.bottom);
      v11 = RectRgn;
      if ( RectRgn )
        CombineRgn(RectRgn, RectRgn, a3, 1);
      else
        v11 = a3;
      if ( !a2 )
      {
        p_rcDst = 0;
        goto LABEL_12;
      }
    }
    else
    {
      v11 = 0;
      if ( !a2 )
        goto LABEL_12;
    }
    IntersectRect(&rcDst, &rcDst, a2);
  }
LABEL_12:
  CurrentThreadId = GetCurrentThreadId();
  WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)this + 7), 0);
  v14 = 129;
  if ( *((_DWORD *)this + 213) != 1 )
    v14 = 1;
  v15 = (a4 != 0 ? 4 : 0) | v14;
  if ( CurrentThreadId == WindowThreadProcessId )
    v16 = RedrawWindow(*((HWND *)this + 7), p_rcDst, v11, v15);
  else
    v16 = CInvalidateMgr::PostInvalidate((CInkOverlay *)((char *)this + 680), *((HWND *)this + 7), p_rcDst, v11, v15);
  v17 = v16;
  if ( v11 && v11 != a3 )
    DeleteObject(v11);
  return v17;
}

```

## disassembly

```asm
0x1800e0ab0  push    rbx
0x1800e0ab2  push    rbp
0x1800e0ab3  push    rsi
0x1800e0ab4  push    rdi
0x1800e0ab5  push    r12
0x1800e0ab7  push    r14
0x1800e0ab9  push    r15
0x1800e0abb  sub     rsp, 50h
0x1800e0abf  mov     rax, cs:__security_cookie
0x1800e0ac6  xor     rax, rsp
0x1800e0ac9  mov     [rsp+88h+var_48], rax
0x1800e0ace  mov     rbx, rdx
0x1800e0ad1  mov     r14, rcx
0x1800e0ad4  lea     rdx, [rcx+150h]; lprcSrc
0x1800e0adb  xorps   xmm0, xmm0
0x1800e0ade  lea     rcx, [rsp+88h+rcDst]; lprcDst
0x1800e0ae3  mov     r15d, r9d
0x1800e0ae6  mov     rsi, r8
0x1800e0ae9  movups  xmmword ptr [rsp+88h+rcDst.left], xmm0
0x1800e0aee  call    cs:__imp_CopyRect
0x1800e0af4  cmp     [rsp+88h+arg_20], 0
0x1800e0afc  mov     r12d, 1
0x1800e0b02  jz      short loc_1800E0B79
0x1800e0b04  lea     rcx, [rsp+88h+rcDst]; lprc
0x1800e0b09  call    cs:__imp_IsRectEmpty
0x1800e0b0f  test    eax, eax
0x1800e0b11  jnz     short loc_1800E0B79
0x1800e0b13  lea     rbp, [rsp+88h+rcDst]
0x1800e0b18  test    rsi, rsi
0x1800e0b1b  jz      short loc_1800E0B5D
0x1800e0b1d  mov     r9d, [rsp+88h+rcDst.bottom]; y2
0x1800e0b22  mov     r8d, [rsp+88h+rcDst.right]; x2
0x1800e0b27  mov     edx, [rsp+88h+rcDst.top]; y1
0x1800e0b2b  mov     ecx, [rsp+88h+rcDst.left]; x1
0x1800e0b2f  call    cs:__imp_CreateRectRgn
0x1800e0b35  mov     rdi, rax
0x1800e0b38  test    rax, rax
0x1800e0b3b  jnz     short loc_1800E0B42
0x1800e0b3d  mov     rdi, rsi
0x1800e0b40  jmp     short loc_1800E0B54
0x1800e0b42  mov     r9d, r12d; iMode
0x1800e0b45  mov     r8, rsi; hrgnSrc2
0x1800e0b48  mov     rdx, rax; hrgnSrc1
0x1800e0b4b  mov     rcx, rax; hrgnDst
0x1800e0b4e  call    cs:__imp_CombineRgn
0x1800e0b54  test    rbx, rbx
0x1800e0b57  jnz     short loc_1800E0B64
0x1800e0b59  xor     ebp, ebp
0x1800e0b5b  jmp     short loc_1800E0B7F
0x1800e0b5d  xor     edi, edi
0x1800e0b5f  test    rbx, rbx
0x1800e0b62  jz      short loc_1800E0B7F
0x1800e0b64  mov     r8, rbx; lprcSrc2
0x1800e0b67  lea     rdx, [rsp+88h+rcDst]; lprcSrc1
0x1800e0b6c  lea     rcx, [rsp+88h+rcDst]; lprcDst
0x1800e0b71  call    cs:__imp_IntersectRect
0x1800e0b77  jmp     short loc_1800E0B7F
0x1800e0b79  mov     rdi, rsi
0x1800e0b7c  mov     rbp, rbx
0x1800e0b7f  call    cs:__imp_GetCurrentThreadId
0x1800e0b85  mov     rcx, [r14+38h]; hWnd
0x1800e0b89  xor     edx, edx; lpdwProcessId
0x1800e0b8b  mov     ebx, eax
0x1800e0b8d  call    cs:__imp_GetWindowThreadProcessId
0x1800e0b93  cmp     [r14+354h], r12d
0x1800e0b9a  mov     edx, 81h
0x1800e0b9f  mov     r10, [r14+38h]
0x1800e0ba3  cmovnz  edx, r12d
0x1800e0ba7  neg     r15d
0x1800e0baa  sbb     ecx, ecx
0x1800e0bac  and     ecx, 4
0x1800e0baf  or      edx, ecx
0x1800e0bb1  cmp     ebx, eax
0x1800e0bb3  jnz     short loc_1800E0BC9
0x1800e0bb5  mov     r9d, edx; flags
0x1800e0bb8  mov     r8, rdi; hrgnUpdate
0x1800e0bbb  mov     rdx, rbp; lprcUpdate
0x1800e0bbe  mov     rcx, r10; hWnd
0x1800e0bc1  call    cs:__imp_RedrawWindow
0x1800e0bc7  jmp     short loc_1800E0BE2
0x1800e0bc9  mov     [rsp+88h+var_68], edx; unsigned int
0x1800e0bcd  lea     rcx, [r14+2A8h]; this
0x1800e0bd4  mov     rdx, r10; HWND
0x1800e0bd7  mov     r9, rdi; HRGN
0x1800e0bda  mov     r8, rbp; struct tagRECT *
0x1800e0bdd  call    ?PostInvalidate@CInvalidateMgr@@QEAAHPEAUHWND__@@PEAUtagRECT@@PEAUHRGN__@@I@Z; CInvalidateMgr::PostInvalidate(HWND__ *,tagRECT *,HRGN__ *,uint)
0x1800e0be2  mov     ebx, eax
0x1800e0be4  test    rdi, rdi
0x1800e0be7  jz      short loc_1800E0BF7
0x1800e0be9  cmp     rdi, rsi
0x1800e0bec  jz      short loc_1800E0BF7
0x1800e0bee  mov     rcx, rdi; ho
0x1800e0bf1  call    cs:__imp_DeleteObject
0x1800e0bf7  mov     eax, ebx
0x1800e0bf9  mov     rcx, [rsp+88h+var_48]
0x1800e0bfe  xor     rcx, rsp; StackCookie
0x1800e0c01  call    __security_check_cookie
0x1800e0c06  add     rsp, 50h
0x1800e0c0a  pop     r15
0x1800e0c0c  pop     r14
0x1800e0c0e  pop     r12
0x1800e0c10  pop     rdi
0x1800e0c11  pop     rsi
0x1800e0c12  pop     rbp
0x1800e0c13  pop     rbx
0x1800e0c14  retn
```
