# CWispInk::GetEMF(HENHMETAFILE__ * &)

- ea: `0x18009804c`
- end: `0x180098283`
- name: `?GetEMF@CWispInk@@IEAAJAEAPEAUHENHMETAFILE__@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(CWispInk *__hidden this, HENHMETAFILE *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180097d58`
- `0x180097f20`

## callees

- `0x18000c788`
- `0x18000f0d0`
- `0x180010350`
- `0x180028190`
- `0x180036e80`
- `0x18003b6a4`
- `0x1800890b0`
- `0x18009804c`
- `0x18009828c`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800980bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800980bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098244`
- `USER32!OffsetRect` at `0x1800980ea`
- `USER32!OffsetRect` at `0x180098100`
- `USER32!OffsetRect` at `0x1800980ea`
- `USER32!OffsetRect` at `0x180098100`
- `USER32!GetDC` at `0x1800980b1`
- `USER32!GetDC` at `0x1800980b1`
- `USER32!ReleaseDC` at `0x180098120`
- `USER32!ReleaseDC` at `0x180098120`
- `GDI32!SetMapMode` at `0x180098137`
- `GDI32!SetMapMode` at `0x180098137`
- `GDI32!SetViewportOrgEx` at `0x180098163`
- `GDI32!SetViewportOrgEx` at `0x180098163`
- `GDI32!SetWindowOrgEx` at `0x180098150`
- `GDI32!SetWindowOrgEx` at `0x180098150`
- `GDI32!CreateEnhMetaFileW` at `0x180098112`
- `GDI32!CreateEnhMetaFileW` at `0x180098112`
- `GDI32!CloseEnhMetaFile` at `0x180098225`
- `GDI32!CloseEnhMetaFile` at `0x180098225`
- `GDI32!DeleteEnhMetaFile` at `0x180098235`
- `GDI32!DeleteEnhMetaFile` at `0x180098235`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall CWispInk::GetEMF(CInkStroke **this, HENHMETAFILE *a2)
{
  HDC DC; // rbx
  signed int result; // eax
  HDC v6; // rsi
  int v7; // ebx
  CInkStroke *v8; // rdi
  CInkStroke *v9; // r15
  float v10; // xmm0_4
  CCanvas *v11; // rax
  HENHMETAFILE v12; // rax
  signed int LastError; // eax
  bool v14[8]; // [rsp+38h] [rbp-49h] BYREF
  CCanvas *v15; // [rsp+40h] [rbp-41h]
  CCanvas *v16; // [rsp+48h] [rbp-39h]
  RECT v17; // [rsp+50h] [rbp-31h] BYREF
  struct tagRECT rc; // [rsp+60h] [rbp-21h] BYREF
  struct tagXFORM v19; // [rsp+70h] [rbp-11h] BYREF
  struct tagRECT v20; // [rsp+88h] [rbp+7h] BYREF

  *a2 = 0;
  CWispInk::GetInkRect((CWispInk *)this, &rc, 1, 0, 0);
  CWispInk::GetInkRect((CWispInk *)this, &v17, 0, 0, 1);
  DC = GetDC(0);
  if ( DC )
  {
    OffsetRect(&rc, -v17.left, -v17.top);
    OffsetRect(&v17, -v17.left, -v17.top);
    v6 = CreateEnhMetaFileW(DC, 0, &v17, 0);
    ReleaseDC(0, DC);
    if ( v6 )
    {
      v7 = 0;
      SetMapMode(v6, 3);
      rc.top = -rc.top;
      rc.bottom = -rc.bottom;
      SetWindowOrgEx(v6, v17.left, v17.top, 0);
      SetViewportOrgEx(v6, v17.left, v17.top, 0);
      CWispInk::GetBoundingBox((CWispInk *)this, &v20, 0);
      memset(&v19, 0, sizeof(v19));
      MapRectToRect(&v20, &rc, &v19);
      v8 = this[9];
      v9 = (CInkStroke *)((char *)v8 + 24 * (_QWORD)this[10]);
      v10 = MinPenDim(v6);
      while ( v9 != v8 && v7 >= 0 )
      {
        v11 = (CCanvas *)WinMalloc(0x150u);
        v16 = v11;
        if ( v11 )
          v11 = CCanvas::CCanvas(v11, v6);
        v14[0] = v11 != 0;
        v15 = v11;
        if ( v11 )
          v7 = CInkStroke::Draw(v8, v11, 0, &v19, v10, 0);
        else
          v7 = -2147024882;
        AutoPtr<CBezierForFiller>::~AutoPtr<CBezierForFiller>(v14);
        v8 = (CInkStroke *)((char *)v8 + 24);
      }
      v12 = CloseEnhMetaFile(v6);
      *a2 = v12;
      if ( v7 < 0 )
      {
        DeleteEnhMetaFile(v12);
        *a2 = 0;
      }
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    return v7;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18009804c  mov     rax, rsp
0x18009804f  mov     [rax+18h], rbx
0x180098053  push    rbp
0x180098054  push    rsi
0x180098055  push    rdi
0x180098056  push    r14
0x180098058  push    r15
0x18009805a  lea     rbp, [rax-5Fh]
0x18009805e  sub     rsp, 0B0h
0x180098065  movaps  xmmword ptr [rax-38h], xmm6
0x180098069  mov     rax, cs:__security_cookie
0x180098070  xor     rax, rsp
0x180098073  mov     [rbp+57h+var_40], rax
0x180098077  mov     r14, rdx
0x18009807a  mov     r15, rcx
0x18009807d  mov     qword ptr [rdx], 0
0x180098084  mov     byte ptr [rsp+0D0h+var_B0], 0; bool
0x180098089  xor     r9d, r9d; bool
0x18009808c  mov     r8b, 1; bool
0x18009808f  lea     rdx, [rbp+57h+rc]; lprc
0x180098093  call    ?GetInkRect@CWispInk@@IEBA?AUtagRECT@@_N00@Z; CWispInk::GetInkRect(bool,bool,bool)
0x180098098  mov     byte ptr [rsp+0D0h+var_B0], 1; bool
0x18009809d  xor     r9d, r9d; bool
0x1800980a0  xor     r8d, r8d; bool
0x1800980a3  lea     rdx, [rbp+57h+var_88]; lprc
0x1800980a7  mov     rcx, r15; this
0x1800980aa  call    ?GetInkRect@CWispInk@@IEBA?AUtagRECT@@_N00@Z; CWispInk::GetInkRect(bool,bool,bool)
0x1800980af  xor     ecx, ecx; hWnd
0x1800980b1  call    cs:__imp_GetDC
0x1800980b7  mov     rbx, rax
0x1800980ba  test    rax, rax
0x1800980bd  jnz     short loc_1800980DA
0x1800980bf  call    cs:__imp_GetLastError
0x1800980c5  test    eax, eax
0x1800980c7  jle     loc_18009825B
0x1800980cd  movzx   eax, ax
0x1800980d0  or      eax, 80070000h
0x1800980d5  jmp     loc_18009825B
0x1800980da  mov     r8d, [rbp+57h+var_88.top]
0x1800980de  neg     r8d; dy
0x1800980e1  mov     edx, [rbp+57h+var_88.left]
0x1800980e4  neg     edx; dx
0x1800980e6  lea     rcx, [rbp+57h+rc]; lprc
0x1800980ea  call    cs:__imp_OffsetRect
0x1800980f0  mov     r8d, [rbp+57h+var_88.top]
0x1800980f4  neg     r8d; dy
0x1800980f7  mov     edx, [rbp+57h+var_88.left]
0x1800980fa  neg     edx; dx
0x1800980fc  lea     rcx, [rbp+57h+var_88]; lprc
0x180098100  call    cs:__imp_OffsetRect
0x180098106  xor     r9d, r9d; lpDesc
0x180098109  lea     r8, [rbp+57h+var_88]; lprc
0x18009810d  xor     edx, edx; lpFilename
0x18009810f  mov     rcx, rbx; hdc
0x180098112  call    cs:__imp_CreateEnhMetaFileW
0x180098118  mov     rsi, rax
0x18009811b  mov     rdx, rbx; hDC
0x18009811e  xor     ecx, ecx; hWnd
0x180098120  call    cs:__imp_ReleaseDC
0x180098126  test    rsi, rsi
0x180098129  jz      loc_180098244
0x18009812f  xor     ebx, ebx
0x180098131  lea     edx, [rbx+3]; iMode
0x180098134  mov     rcx, rsi; hdc
0x180098137  call    cs:__imp_SetMapMode
0x18009813d  neg     [rbp+57h+rc.top]
0x180098140  neg     [rbp+57h+rc.bottom]
0x180098143  xor     r9d, r9d; lppt
0x180098146  mov     r8d, [rbp+57h+var_88.top]; y
0x18009814a  mov     edx, [rbp+57h+var_88.left]; x
0x18009814d  mov     rcx, rsi; hdc
0x180098150  call    cs:__imp_SetWindowOrgEx
0x180098156  xor     r9d, r9d; lppt
0x180098159  mov     r8d, [rbp+57h+var_88.top]; y
0x18009815d  mov     edx, [rbp+57h+var_88.left]; x
0x180098160  mov     rcx, rsi; hdc
0x180098163  call    cs:__imp_SetViewportOrgEx
0x180098169  xor     r8d, r8d; unsigned int
0x18009816c  lea     rdx, [rbp+57h+var_50]; retstr
0x180098170  mov     rcx, r15; this
0x180098173  call    ?GetBoundingBox@CWispInk@@QEBA?AUtagRECT@@K@Z; CWispInk::GetBoundingBox(ulong)
0x180098178  xorps   xmm0, xmm0
0x18009817b  xor     eax, eax
0x18009817d  movups  xmmword ptr [rbp+57h+var_68.eM11], xmm0
0x180098181  mov     qword ptr [rbp+57h+var_68.eDx], rax
0x180098185  lea     r8, [rbp+57h+var_68]; struct tagXFORM *
0x180098189  lea     rdx, [rbp+57h+rc]; struct tagRECT *
0x18009818d  lea     rcx, [rbp+57h+var_50]; struct tagRECT *
0x180098191  call    ?MapRectToRect@@YAXAEBUtagRECT@@0AEAUtagXFORM@@@Z; MapRectToRect(tagRECT const &,tagRECT const &,tagXFORM &)
0x180098196  mov     rdi, [r15+48h]
0x18009819a  mov     rax, [r15+50h]
0x18009819e  lea     rcx, [rax+rax*2]
0x1800981a2  lea     r15, [rdi+rcx*8]
0x1800981a6  mov     rcx, rsi; hdc
0x1800981a9  call    ?MinPenDim@@YAMPEAUHDC__@@@Z; MinPenDim(HDC__ *)
0x1800981ae  movaps  xmm6, xmm0
0x1800981b1  jmp     short loc_18009821D
0x1800981b3  test    ebx, ebx
0x1800981b5  js      short loc_180098222
0x1800981b7  mov     ecx, 150h; unsigned __int64
0x1800981bc  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800981c1  mov     [rbp+57h+var_90], rax
0x1800981c5  test    rax, rax
0x1800981c8  jz      short loc_1800981D6
0x1800981ca  mov     rdx, rsi; HDC
0x1800981cd  mov     rcx, rax; this
0x1800981d0  call    ??0CCanvas@@QEAA@PEAUHDC__@@@Z; CCanvas::CCanvas(HDC__ *)
0x1800981d5  nop
0x1800981d6  test    rax, rax
0x1800981d9  setnz   [rbp+57h+var_A0]
0x1800981dd  mov     [rbp+57h+var_98], rax
0x1800981e1  test    rax, rax
0x1800981e4  jz      short loc_18009820B
0x1800981e6  mov     [rsp+0D0h+var_A8], 0; struct DrAt *
0x1800981ef  movss   [rsp+0D0h+var_B0], xmm6; float
0x1800981f5  lea     r9, [rbp+57h+var_68]; struct tagXFORM *
0x1800981f9  xor     r8d, r8d; struct tagXFORM *
0x1800981fc  mov     rdx, rax; struct CCanvas *
0x1800981ff  mov     rcx, rdi; this
0x180098202  call    ?Draw@CInkStroke@@QEBAJPEAVCCanvas@@PEBUtagXFORM@@1MPEAVDrAt@@@Z; CInkStroke::Draw(CCanvas *,tagXFORM const *,tagXFORM const *,float,DrAt *)
0x180098207  mov     ebx, eax
0x180098209  jmp     short loc_180098210
0x18009820b  mov     ebx, 8007000Eh
0x180098210  lea     rcx, [rbp+57h+var_A0]
0x180098214  call    ??1?$AutoPtr@VCBezierForFiller@@@@QEAA@XZ; AutoPtr<CBezierForFiller>::~AutoPtr<CBezierForFiller>(void)
0x180098219  add     rdi, 18h
0x18009821d  cmp     r15, rdi
0x180098220  jnz     short loc_1800981B3
0x180098222  mov     rcx, rsi; hdc
0x180098225  call    cs:__imp_CloseEnhMetaFile
0x18009822b  mov     [r14], rax
0x18009822e  test    ebx, ebx
0x180098230  jns     short loc_180098259
0x180098232  mov     rcx, rax; hmf
0x180098235  call    cs:__imp_DeleteEnhMetaFile
0x18009823b  mov     qword ptr [r14], 0
0x180098242  jmp     short loc_180098259
0x180098244  call    cs:__imp_GetLastError
0x18009824a  mov     ebx, eax
0x18009824c  test    eax, eax
0x18009824e  jle     short loc_180098259
0x180098250  movzx   ebx, ax
0x180098253  or      ebx, 80070000h
0x180098259  mov     eax, ebx
0x18009825b  mov     rcx, [rbp+57h+var_40]
0x18009825f  xor     rcx, rsp; StackCookie
0x180098262  call    __security_check_cookie
0x180098267  lea     r11, [rsp+0D0h+var_20]
0x18009826f  mov     rbx, [r11+40h]
0x180098273  movaps  xmm6, xmmword ptr [r11-10h]
0x180098278  mov     rsp, r11
0x18009827b  pop     r15
0x18009827d  pop     r14
0x18009827f  pop     rdi
0x180098280  pop     rsi
0x180098281  pop     rbp
0x180098282  retn
```
