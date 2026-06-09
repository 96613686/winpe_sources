# CInkPicture::_InvalidateWindow(tagRECT *,HRGN__ *,int,int)

- ea: `0x1800f1088`
- end: `0x1800f11dc`
- name: `?_InvalidateWindow@CInkPicture@@AEAAHPEAUtagRECT@@PEAUHRGN__@@HH@Z`
- size: `340`
- prototype: `int(CInkPicture *__hidden this, struct tagRECT *, HRGN, int, int)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e6fe0`
- `0x1800ef5ac`
- `0x1800efe58`
- `0x1800f1928`
- `0x1800f24b0`
- `0x1800f26f4`
- `0x1800f6cd0`

## callees

- `0x1800c9fac`
- `0x1800f1088`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f114b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f114b`
- `USER32!IsRectEmpty` at `0x1800f10d2`
- `USER32!IsRectEmpty` at `0x1800f10d2`
- `USER32!CopyRect` at `0x1800f10c7`
- `USER32!CopyRect` at `0x1800f10c7`
- `USER32!RedrawWindow` at `0x1800f1183`
- `USER32!RedrawWindow` at `0x1800f1183`
- `USER32!GetWindowThreadProcessId` at `0x1800f115c`
- `USER32!GetWindowThreadProcessId` at `0x1800f115c`
- `USER32!IntersectRect` at `0x1800f113d`
- `USER32!IntersectRect` at `0x1800f113d`
- `GDI32!CombineRgn` at `0x1800f111a`
- `GDI32!CombineRgn` at `0x1800f111a`
- `GDI32!CreateRectRgn` at `0x1800f10f8`
- `GDI32!CreateRectRgn` at `0x1800f10f8`
- `GDI32!DeleteObject` at `0x1800f11b3`
- `GDI32!DeleteObject` at `0x1800f11b3`

## pseudocode

```c
__int64 __fastcall CInkPicture::_InvalidateWindow(CInkPicture *this, struct tagRECT *a2, HRGN a3, int a4)
{
  struct tagRECT *p_rcDst; // rbp
  HRGN RectRgn; // rax
  HRGN v10; // rdi
  DWORD CurrentThreadId; // ebx
  DWORD WindowThreadProcessId; // eax
  UINT v13; // edx
  int v14; // eax
  unsigned int v15; // ebx
  struct tagRECT rcDst; // [rsp+30h] [rbp-48h] BYREF

  rcDst = 0;
  CopyRect(&rcDst, (const RECT *)this + 35);
  if ( IsRectEmpty(&rcDst) )
  {
    v10 = a3;
    p_rcDst = a2;
  }
  else
  {
    p_rcDst = &rcDst;
    if ( a3 )
    {
      RectRgn = CreateRectRgn(rcDst.left, rcDst.top, rcDst.right, rcDst.bottom);
      v10 = RectRgn;
      if ( RectRgn )
        CombineRgn(RectRgn, RectRgn, a3, 1);
      else
        v10 = a3;
      if ( !a2 )
      {
        p_rcDst = 0;
        goto LABEL_11;
      }
    }
    else
    {
      v10 = 0;
      if ( !a2 )
        goto LABEL_11;
    }
    IntersectRect(&rcDst, &rcDst, a2);
  }
LABEL_11:
  CurrentThreadId = GetCurrentThreadId();
  WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)this + 21), 0);
  v13 = a4 != 0 ? 5 : 1;
  if ( CurrentThreadId == WindowThreadProcessId )
    v14 = RedrawWindow(*((HWND *)this + 21), p_rcDst, v10, v13);
  else
    v14 = CInvalidateMgr::PostInvalidate((CInkPicture *)((char *)this + 904), *((HWND *)this + 21), p_rcDst, v10, v13);
  v15 = v14;
  if ( v10 && v10 != a3 )
    DeleteObject(v10);
  return v15;
}

```

## disassembly

```asm
0x1800f1088  mov     [rsp+arg_18], rbx
0x1800f108d  push    rbp
0x1800f108e  push    rsi
0x1800f108f  push    rdi
0x1800f1090  push    r14
0x1800f1092  push    r15
0x1800f1094  sub     rsp, 50h
0x1800f1098  mov     rax, cs:__security_cookie
0x1800f109f  xor     rax, rsp
0x1800f10a2  mov     [rsp+78h+var_38], rax
0x1800f10a7  mov     rbx, rdx
0x1800f10aa  mov     r14, rcx
0x1800f10ad  lea     rdx, [rcx+230h]; lprcSrc
0x1800f10b4  xorps   xmm0, xmm0
0x1800f10b7  lea     rcx, [rsp+78h+rcDst]; lprcDst
0x1800f10bc  mov     r15d, r9d
0x1800f10bf  mov     rsi, r8
0x1800f10c2  movups  xmmword ptr [rsp+78h+rcDst.left], xmm0
0x1800f10c7  call    cs:__imp_CopyRect
0x1800f10cd  lea     rcx, [rsp+78h+rcDst]; lprc
0x1800f10d2  call    cs:__imp_IsRectEmpty
0x1800f10d8  test    eax, eax
0x1800f10da  jnz     short loc_1800F1145
0x1800f10dc  lea     rbp, [rsp+78h+rcDst]
0x1800f10e1  test    rsi, rsi
0x1800f10e4  jz      short loc_1800F1129
0x1800f10e6  mov     r9d, [rsp+78h+rcDst.bottom]; y2
0x1800f10eb  mov     r8d, [rsp+78h+rcDst.right]; x2
0x1800f10f0  mov     edx, [rsp+78h+rcDst.top]; y1
0x1800f10f4  mov     ecx, [rsp+78h+rcDst.left]; x1
0x1800f10f8  call    cs:__imp_CreateRectRgn
0x1800f10fe  mov     rdi, rax
0x1800f1101  test    rax, rax
0x1800f1104  jnz     short loc_1800F110B
0x1800f1106  mov     rdi, rsi
0x1800f1109  jmp     short loc_1800F1120
0x1800f110b  mov     r9d, 1; iMode
0x1800f1111  mov     r8, rsi; hrgnSrc2
0x1800f1114  mov     rdx, rax; hrgnSrc1
0x1800f1117  mov     rcx, rax; hrgnDst
0x1800f111a  call    cs:__imp_CombineRgn
0x1800f1120  test    rbx, rbx
0x1800f1123  jnz     short loc_1800F1130
0x1800f1125  xor     ebp, ebp
0x1800f1127  jmp     short loc_1800F114B
0x1800f1129  xor     edi, edi
0x1800f112b  test    rbx, rbx
0x1800f112e  jz      short loc_1800F114B
0x1800f1130  mov     r8, rbx; lprcSrc2
0x1800f1133  lea     rdx, [rsp+78h+rcDst]; lprcSrc1
0x1800f1138  lea     rcx, [rsp+78h+rcDst]; lprcDst
0x1800f113d  call    cs:__imp_IntersectRect
0x1800f1143  jmp     short loc_1800F114B
0x1800f1145  mov     rdi, rsi
0x1800f1148  mov     rbp, rbx
0x1800f114b  call    cs:__imp_GetCurrentThreadId
0x1800f1151  mov     rcx, [r14+0A8h]; hWnd
0x1800f1158  xor     edx, edx; lpdwProcessId
0x1800f115a  mov     ebx, eax
0x1800f115c  call    cs:__imp_GetWindowThreadProcessId
0x1800f1162  mov     r10, [r14+0A8h]
0x1800f1169  neg     r15d
0x1800f116c  sbb     edx, edx
0x1800f116e  and     edx, 4
0x1800f1171  inc     edx
0x1800f1173  cmp     ebx, eax
0x1800f1175  jnz     short loc_1800F118B
0x1800f1177  mov     r9d, edx; flags
0x1800f117a  mov     r8, rdi; hrgnUpdate
0x1800f117d  mov     rdx, rbp; lprcUpdate
0x1800f1180  mov     rcx, r10; hWnd
0x1800f1183  call    cs:__imp_RedrawWindow
0x1800f1189  jmp     short loc_1800F11A4
0x1800f118b  mov     [rsp+78h+var_58], edx; unsigned int
0x1800f118f  lea     rcx, [r14+388h]; this
0x1800f1196  mov     rdx, r10; HWND
0x1800f1199  mov     r9, rdi; HRGN
0x1800f119c  mov     r8, rbp; struct tagRECT *
0x1800f119f  call    ?PostInvalidate@CInvalidateMgr@@QEAAHPEAUHWND__@@PEAUtagRECT@@PEAUHRGN__@@I@Z; CInvalidateMgr::PostInvalidate(HWND__ *,tagRECT *,HRGN__ *,uint)
0x1800f11a4  mov     ebx, eax
0x1800f11a6  test    rdi, rdi
0x1800f11a9  jz      short loc_1800F11B9
0x1800f11ab  cmp     rdi, rsi
0x1800f11ae  jz      short loc_1800F11B9
0x1800f11b0  mov     rcx, rdi; ho
0x1800f11b3  call    cs:__imp_DeleteObject
0x1800f11b9  mov     eax, ebx
0x1800f11bb  mov     rcx, [rsp+78h+var_38]
0x1800f11c0  xor     rcx, rsp; StackCookie
0x1800f11c3  call    __security_check_cookie
0x1800f11c8  mov     rbx, [rsp+78h+arg_18]
0x1800f11d0  add     rsp, 50h
0x1800f11d4  pop     r15
0x1800f11d6  pop     r14
0x1800f11d8  pop     rdi
0x1800f11d9  pop     rsi
0x1800f11da  pop     rbp
0x1800f11db  retn
```
