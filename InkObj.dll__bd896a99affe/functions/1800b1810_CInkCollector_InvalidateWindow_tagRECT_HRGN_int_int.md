# CInkCollector::_InvalidateWindow(tagRECT *,HRGN__ *,int,int)

- ea: `0x1800b1810`
- end: `0x1800b1966`
- name: `?_InvalidateWindow@CInkCollector@@AEAAHPEAUtagRECT@@PEAUHRGN__@@HH@Z`
- size: `342`
- prototype: `int(CInkCollector *__hidden this, struct tagRECT *, HRGN, int, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800aadf0`
- `0x1800ad9a8`
- `0x1800b25d8`
- `0x1800b5420`

## callees

- `0x1800b1810`
- `0x1800c9fac`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b18dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b18dd`
- `USER32!IsRectEmpty` at `0x1800b1864`
- `USER32!IsRectEmpty` at `0x1800b1864`
- `USER32!CopyRect` at `0x1800b184f`
- `USER32!CopyRect` at `0x1800b184f`
- `USER32!RedrawWindow` at `0x1800b190c`
- `USER32!RedrawWindow` at `0x1800b190c`
- `USER32!GetWindowThreadProcessId` at `0x1800b18eb`
- `USER32!GetWindowThreadProcessId` at `0x1800b18eb`
- `USER32!IntersectRect` at `0x1800b18cf`
- `USER32!IntersectRect` at `0x1800b18cf`
- `GDI32!CombineRgn` at `0x1800b18ac`
- `GDI32!CombineRgn` at `0x1800b18ac`
- `GDI32!CreateRectRgn` at `0x1800b188a`
- `GDI32!CreateRectRgn` at `0x1800b188a`
- `GDI32!DeleteObject` at `0x1800b193d`
- `GDI32!DeleteObject` at `0x1800b193d`

## pseudocode

```c
__int64 __fastcall CInkCollector::_InvalidateWindow(CInkCollector *this, struct tagRECT *a2, HRGN a3, int a4, int a5)
{
  struct tagRECT *p_rcDst; // rbp
  HRGN RectRgn; // rax
  HRGN v11; // rdi
  DWORD CurrentThreadId; // ebx
  DWORD WindowThreadProcessId; // eax
  UINT v14; // edx
  int v15; // eax
  unsigned int v16; // ebx
  struct tagRECT rcDst; // [rsp+30h] [rbp-48h] BYREF

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
  v14 = a4 != 0 ? 5 : 1;
  if ( CurrentThreadId == WindowThreadProcessId )
    v15 = RedrawWindow(*((HWND *)this + 7), p_rcDst, v11, v14);
  else
    v15 = CInvalidateMgr::PostInvalidate((CInkCollector *)((char *)this + 664), *((HWND *)this + 7), p_rcDst, v11, v14);
  v16 = v15;
  if ( v11 && v11 != a3 )
    DeleteObject(v11);
  return v16;
}

```

## disassembly

```asm
0x1800b1810  mov     [rsp+arg_18], rbx
0x1800b1815  push    rbp
0x1800b1816  push    rsi
0x1800b1817  push    rdi
0x1800b1818  push    r14
0x1800b181a  push    r15
0x1800b181c  sub     rsp, 50h
0x1800b1820  mov     rax, cs:__security_cookie
0x1800b1827  xor     rax, rsp
0x1800b182a  mov     [rsp+78h+var_38], rax
0x1800b182f  mov     rbx, rdx
0x1800b1832  mov     r14, rcx
0x1800b1835  lea     rdx, [rcx+150h]; lprcSrc
0x1800b183c  xorps   xmm0, xmm0
0x1800b183f  lea     rcx, [rsp+78h+rcDst]; lprcDst
0x1800b1844  mov     r15d, r9d
0x1800b1847  mov     rsi, r8
0x1800b184a  movups  xmmword ptr [rsp+78h+rcDst.left], xmm0
0x1800b184f  call    cs:__imp_CopyRect
0x1800b1855  cmp     [rsp+78h+arg_20], 0
0x1800b185d  jz      short loc_1800B18D7
0x1800b185f  lea     rcx, [rsp+78h+rcDst]; lprc
0x1800b1864  call    cs:__imp_IsRectEmpty
0x1800b186a  test    eax, eax
0x1800b186c  jnz     short loc_1800B18D7
0x1800b186e  lea     rbp, [rsp+78h+rcDst]
0x1800b1873  test    rsi, rsi
0x1800b1876  jz      short loc_1800B18BB
0x1800b1878  mov     r9d, [rsp+78h+rcDst.bottom]; y2
0x1800b187d  mov     r8d, [rsp+78h+rcDst.right]; x2
0x1800b1882  mov     edx, [rsp+78h+rcDst.top]; y1
0x1800b1886  mov     ecx, [rsp+78h+rcDst.left]; x1
0x1800b188a  call    cs:__imp_CreateRectRgn
0x1800b1890  mov     rdi, rax
0x1800b1893  test    rax, rax
0x1800b1896  jnz     short loc_1800B189D
0x1800b1898  mov     rdi, rsi
0x1800b189b  jmp     short loc_1800B18B2
0x1800b189d  mov     r9d, 1; iMode
0x1800b18a3  mov     r8, rsi; hrgnSrc2
0x1800b18a6  mov     rdx, rax; hrgnSrc1
0x1800b18a9  mov     rcx, rax; hrgnDst
0x1800b18ac  call    cs:__imp_CombineRgn
0x1800b18b2  test    rbx, rbx
0x1800b18b5  jnz     short loc_1800B18C2
0x1800b18b7  xor     ebp, ebp
0x1800b18b9  jmp     short loc_1800B18DD
0x1800b18bb  xor     edi, edi
0x1800b18bd  test    rbx, rbx
0x1800b18c0  jz      short loc_1800B18DD
0x1800b18c2  mov     r8, rbx; lprcSrc2
0x1800b18c5  lea     rdx, [rsp+78h+rcDst]; lprcSrc1
0x1800b18ca  lea     rcx, [rsp+78h+rcDst]; lprcDst
0x1800b18cf  call    cs:__imp_IntersectRect
0x1800b18d5  jmp     short loc_1800B18DD
0x1800b18d7  mov     rdi, rsi
0x1800b18da  mov     rbp, rbx
0x1800b18dd  call    cs:__imp_GetCurrentThreadId
0x1800b18e3  mov     rcx, [r14+38h]; hWnd
0x1800b18e7  xor     edx, edx; lpdwProcessId
0x1800b18e9  mov     ebx, eax
0x1800b18eb  call    cs:__imp_GetWindowThreadProcessId
0x1800b18f1  neg     r15d
0x1800b18f4  sbb     edx, edx
0x1800b18f6  and     edx, 4
0x1800b18f9  inc     edx
0x1800b18fb  cmp     ebx, eax
0x1800b18fd  jnz     short loc_1800B1914
0x1800b18ff  mov     rcx, [r14+38h]; hWnd
0x1800b1903  mov     r9d, edx; flags
0x1800b1906  mov     rdx, rbp; lprcUpdate
0x1800b1909  mov     r8, rdi; hrgnUpdate
0x1800b190c  call    cs:__imp_RedrawWindow
0x1800b1912  jmp     short loc_1800B192E
0x1800b1914  mov     [rsp+78h+var_58], edx; unsigned int
0x1800b1918  lea     rcx, [r14+298h]; this
0x1800b191f  mov     rdx, [r14+38h]; HWND
0x1800b1923  mov     r9, rdi; HRGN
0x1800b1926  mov     r8, rbp; struct tagRECT *
0x1800b1929  call    ?PostInvalidate@CInvalidateMgr@@QEAAHPEAUHWND__@@PEAUtagRECT@@PEAUHRGN__@@I@Z; CInvalidateMgr::PostInvalidate(HWND__ *,tagRECT *,HRGN__ *,uint)
0x1800b192e  mov     ebx, eax
0x1800b1930  test    rdi, rdi
0x1800b1933  jz      short loc_1800B1943
0x1800b1935  cmp     rdi, rsi
0x1800b1938  jz      short loc_1800B1943
0x1800b193a  mov     rcx, rdi; ho
0x1800b193d  call    cs:__imp_DeleteObject
0x1800b1943  mov     eax, ebx
0x1800b1945  mov     rcx, [rsp+78h+var_38]
0x1800b194a  xor     rcx, rsp; StackCookie
0x1800b194d  call    __security_check_cookie
0x1800b1952  mov     rbx, [rsp+78h+arg_18]
0x1800b195a  add     rsp, 50h
0x1800b195e  pop     r15
0x1800b1960  pop     r14
0x1800b1962  pop     rdi
0x1800b1963  pop     rsi
0x1800b1964  pop     rbp
0x1800b1965  retn
```
