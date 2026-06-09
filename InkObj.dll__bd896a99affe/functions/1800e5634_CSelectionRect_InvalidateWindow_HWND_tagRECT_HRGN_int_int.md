# CSelectionRect::_InvalidateWindow(HWND__ *,tagRECT *,HRGN__ *,int,int)

- ea: `0x1800e5634`
- end: `0x1800e5785`
- name: `?_InvalidateWindow@CSelectionRect@@AEAAHPEAUHWND__@@PEAUtagRECT@@PEAUHRGN__@@HH@Z`
- size: `337`
- prototype: `int(CSelectionRect *__hidden this, HWND, struct tagRECT *, HRGN, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800dd08c`
- `0x1800dd478`
- `0x1800e5160`

## callees

- `0x1800c9fac`
- `0x1800e5634`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e56f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e56f6`
- `USER32!IsRectEmpty` at `0x1800e567a`
- `USER32!IsRectEmpty` at `0x1800e567a`
- `USER32!CopyRect` at `0x1800e566f`
- `USER32!CopyRect` at `0x1800e566f`
- `USER32!RedrawWindow` at `0x1800e5734`
- `USER32!RedrawWindow` at `0x1800e5734`
- `USER32!GetWindowThreadProcessId` at `0x1800e5703`
- `USER32!GetWindowThreadProcessId` at `0x1800e5703`
- `USER32!IntersectRect` at `0x1800e56e8`
- `USER32!IntersectRect` at `0x1800e56e8`
- `GDI32!CombineRgn` at `0x1800e56c5`
- `GDI32!CombineRgn` at `0x1800e56c5`
- `GDI32!CreateRectRgn` at `0x1800e56a6`
- `GDI32!CreateRectRgn` at `0x1800e56a6`
- `GDI32!DeleteObject` at `0x1800e5761`
- `GDI32!DeleteObject` at `0x1800e5761`

## pseudocode

```c
__int64 __fastcall CSelectionRect::_InvalidateWindow(
        CSelectionRect *this,
        HWND a2,
        struct tagRECT *a3,
        HRGN a4,
        int a5)
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
  CopyRect(&rcDst, (const RECT *)this + 2);
  if ( IsRectEmpty(&rcDst) )
  {
    v11 = a4;
    p_rcDst = a3;
  }
  else
  {
    p_rcDst = &rcDst;
    if ( a4 )
    {
      RectRgn = CreateRectRgn(rcDst.left, rcDst.top, rcDst.right, rcDst.bottom);
      v11 = RectRgn;
      if ( RectRgn )
        CombineRgn(RectRgn, RectRgn, a4, 1);
      else
        v11 = a4;
      if ( !a3 )
      {
        p_rcDst = 0;
        goto LABEL_11;
      }
    }
    else
    {
      v11 = 0;
      if ( !a3 )
        goto LABEL_11;
    }
    IntersectRect(&rcDst, &rcDst, a3);
  }
LABEL_11:
  CurrentThreadId = GetCurrentThreadId();
  WindowThreadProcessId = GetWindowThreadProcessId(a2, 0);
  v14 = 129;
  if ( *((_DWORD *)this + 22) != 1 )
    v14 = 1;
  v15 = (a5 != 0 ? 4 : 0) | v14;
  if ( CurrentThreadId == WindowThreadProcessId )
    v16 = RedrawWindow(a2, p_rcDst, v11, v15);
  else
    v16 = CInvalidateMgr::PostInvalidate(*((CInvalidateMgr **)this + 10), a2, p_rcDst, v11, v15);
  v17 = v16;
  if ( v11 && v11 != a4 )
    DeleteObject(v11);
  return v17;
}

```

## disassembly

```asm
0x1800e5634  push    rbx
0x1800e5636  push    rbp
0x1800e5637  push    rsi
0x1800e5638  push    rdi
0x1800e5639  push    r12
0x1800e563b  push    r14
0x1800e563d  push    r15
0x1800e563f  sub     rsp, 50h
0x1800e5643  mov     rax, cs:__security_cookie
0x1800e564a  xor     rax, rsp
0x1800e564d  mov     [rsp+88h+var_48], rax
0x1800e5652  mov     r14, rdx
0x1800e5655  mov     r15, rcx
0x1800e5658  lea     rdx, [rcx+20h]; lprcSrc
0x1800e565c  xorps   xmm0, xmm0
0x1800e565f  lea     rcx, [rsp+88h+rcDst]; lprcDst
0x1800e5664  mov     rsi, r9
0x1800e5667  mov     rbx, r8
0x1800e566a  movups  xmmword ptr [rsp+88h+rcDst.left], xmm0
0x1800e566f  call    cs:__imp_CopyRect
0x1800e5675  lea     rcx, [rsp+88h+rcDst]; lprc
0x1800e567a  call    cs:__imp_IsRectEmpty
0x1800e5680  mov     r12d, 1
0x1800e5686  test    eax, eax
0x1800e5688  jnz     short loc_1800E56F0
0x1800e568a  lea     rbp, [rsp+88h+rcDst]
0x1800e568f  test    rsi, rsi
0x1800e5692  jz      short loc_1800E56D4
0x1800e5694  mov     r9d, [rsp+88h+rcDst.bottom]; y2
0x1800e5699  mov     r8d, [rsp+88h+rcDst.right]; x2
0x1800e569e  mov     edx, [rsp+88h+rcDst.top]; y1
0x1800e56a2  mov     ecx, [rsp+88h+rcDst.left]; x1
0x1800e56a6  call    cs:__imp_CreateRectRgn
0x1800e56ac  mov     rdi, rax
0x1800e56af  test    rax, rax
0x1800e56b2  jnz     short loc_1800E56B9
0x1800e56b4  mov     rdi, rsi
0x1800e56b7  jmp     short loc_1800E56CB
0x1800e56b9  mov     r9d, r12d; iMode
0x1800e56bc  mov     r8, rsi; hrgnSrc2
0x1800e56bf  mov     rdx, rax; hrgnSrc1
0x1800e56c2  mov     rcx, rax; hrgnDst
0x1800e56c5  call    cs:__imp_CombineRgn
0x1800e56cb  test    rbx, rbx
0x1800e56ce  jnz     short loc_1800E56DB
0x1800e56d0  xor     ebp, ebp
0x1800e56d2  jmp     short loc_1800E56F6
0x1800e56d4  xor     edi, edi
0x1800e56d6  test    rbx, rbx
0x1800e56d9  jz      short loc_1800E56F6
0x1800e56db  mov     r8, rbx; lprcSrc2
0x1800e56de  lea     rdx, [rsp+88h+rcDst]; lprcSrc1
0x1800e56e3  lea     rcx, [rsp+88h+rcDst]; lprcDst
0x1800e56e8  call    cs:__imp_IntersectRect
0x1800e56ee  jmp     short loc_1800E56F6
0x1800e56f0  mov     rdi, rsi
0x1800e56f3  mov     rbp, rbx
0x1800e56f6  call    cs:__imp_GetCurrentThreadId
0x1800e56fc  xor     edx, edx; lpdwProcessId
0x1800e56fe  mov     rcx, r14; hWnd
0x1800e5701  mov     ebx, eax
0x1800e5703  call    cs:__imp_GetWindowThreadProcessId
0x1800e5709  cmp     [r15+58h], r12d
0x1800e570d  mov     edx, 81h
0x1800e5712  cmovnz  edx, r12d
0x1800e5716  neg     [rsp+88h+arg_20]
0x1800e571d  sbb     ecx, ecx
0x1800e571f  and     ecx, 4
0x1800e5722  or      edx, ecx
0x1800e5724  cmp     ebx, eax
0x1800e5726  jnz     short loc_1800E573C
0x1800e5728  mov     r9d, edx; flags
0x1800e572b  mov     r8, rdi; hrgnUpdate
0x1800e572e  mov     rdx, rbp; lprcUpdate
0x1800e5731  mov     rcx, r14; hWnd
0x1800e5734  call    cs:__imp_RedrawWindow
0x1800e573a  jmp     short loc_1800E5752
0x1800e573c  mov     rcx, [r15+50h]; this
0x1800e5740  mov     r9, rdi; HRGN
0x1800e5743  mov     [rsp+88h+var_68], edx; unsigned int
0x1800e5747  mov     r8, rbp; struct tagRECT *
0x1800e574a  mov     rdx, r14; HWND
0x1800e574d  call    ?PostInvalidate@CInvalidateMgr@@QEAAHPEAUHWND__@@PEAUtagRECT@@PEAUHRGN__@@I@Z; CInvalidateMgr::PostInvalidate(HWND__ *,tagRECT *,HRGN__ *,uint)
0x1800e5752  mov     ebx, eax
0x1800e5754  test    rdi, rdi
0x1800e5757  jz      short loc_1800E5767
0x1800e5759  cmp     rdi, rsi
0x1800e575c  jz      short loc_1800E5767
0x1800e575e  mov     rcx, rdi; ho
0x1800e5761  call    cs:__imp_DeleteObject
0x1800e5767  mov     eax, ebx
0x1800e5769  mov     rcx, [rsp+88h+var_48]
0x1800e576e  xor     rcx, rsp; StackCookie
0x1800e5771  call    __security_check_cookie
0x1800e5776  add     rsp, 50h
0x1800e577a  pop     r15
0x1800e577c  pop     r14
0x1800e577e  pop     r12
0x1800e5780  pop     rdi
0x1800e5781  pop     rsi
0x1800e5782  pop     rbp
0x1800e5783  pop     rbx
0x1800e5784  retn
```
