# CInkOverlay::_DrawInk(HDC__ *,IInkRectangle *,IInkRenderer *)

- ea: `0x1800df4d8`
- end: `0x1800df7c9`
- name: `?_DrawInk@CInkOverlay@@AEAAJPEAUHDC__@@PEAUIInkRectangle@@PEAUIInkRenderer@@@Z`
- size: `753`
- prototype: `__int64 __fastcall(CInkOverlay *__hidden this, HDC, struct IInkRectangle *, struct IInkRenderer *)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800d9b90`
- `0x1800dc0ec`
- `0x1800dc3d8`

## callees

- `0x180001c20`
- `0x1800217b0`
- `0x1800276c4`
- `0x1800365f8`
- `0x180036824`
- `0x18003c7f4`
- `0x1800a6bf8`
- `0x1800db23c`
- `0x1800db2e8`
- `0x1800df4d8`
- `0x1800df7d0`
- `0x1800e5478`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df654`
- `GDI32!GetClipBox` at `0x1800df56f`
- `GDI32!GetClipBox` at `0x1800df56f`
- `GDI32!ExtSelectClipRgn` at `0x1800df64c`
- `GDI32!ExtSelectClipRgn` at `0x1800df64c`
- `GDI32!CombineRgn` at `0x1800df636`
- `GDI32!CombineRgn` at `0x1800df636`
- `GDI32!GetClipRgn` at `0x1800df60e`
- `GDI32!GetClipRgn` at `0x1800df60e`
- `GDI32!CreateRectRgn` at `0x1800df5fa`
- `GDI32!CreateRectRgn` at `0x1800df5fa`
- `GDI32!DeleteObject` at `0x1800df66c`
- `GDI32!DeleteObject` at `0x1800df66c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CInkOverlay::_DrawInk(CInkOverlay *this, HDC a2, struct IUnknown *a3, struct IInkRenderer *a4)
{
  int v7; // esi
  struct IUnknown *v8; // rbx
  int v9; // r12d
  int v10; // r13d
  HRGN RectRgn; // rax
  HRGN v12; // r15
  int ClipRgn; // eax
  HRGN v14; // rdx
  signed int LastError; // eax
  struct IInkRenderer *v16; // r15
  struct IInkStrokes *v17; // r8
  unsigned int v18; // r8d
  int v20; // [rsp+30h] [rbp-39h] BYREF
  struct IUnknown *v21; // [rsp+38h] [rbp-31h] BYREF
  int v22; // [rsp+40h] [rbp-29h]
  struct IUnknown *v23; // [rsp+48h] [rbp-21h] BYREF
  struct IUnknown *v24[2]; // [rsp+50h] [rbp-19h] BYREF
  struct tagRECT v25; // [rsp+60h] [rbp-9h] BYREF
  struct tagRECT rect; // [rsp+70h] [rbp+7h] BYREF

  v7 = 0;
  v20 = 0;
  v8 = 0;
  v21 = 0;
  v23 = 0;
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&rect, (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
  v9 = *((_DWORD *)this + 101);
  v10 = *((_DWORD *)this + 212);
  v22 = *((_DWORD *)this + 273);
  ATL::AtlComPtrAssign(&v23, *((struct IUnknown **)this + 47));
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&rect);
  if ( a3 )
  {
    ATL::AtlComPtrAssign(&v21, a3);
    v8 = v21;
  }
  else
  {
    rect = 0;
    GetClipBox(a2, &rect);
    v25 = rect;
    CIRect::CIRect((CIRect *)v24, &v25, &v20);
    v7 = v20;
    if ( v20 >= 0 )
    {
      ATL::AtlComPtrAssign(&v21, v24[0]);
      v8 = v21;
    }
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(v24);
  }
  if ( v9 )
  {
    if ( v10 == 1 && v22 == 1 )
    {
      if ( *((_QWORD *)this + 141) )
      {
        RectRgn = CreateRectRgn(0, 0, 0, 0);
        v12 = RectRgn;
        if ( RectRgn )
        {
          ClipRgn = GetClipRgn(a2, RectRgn);
          if ( ClipRgn )
          {
            if ( ClipRgn != 1 )
            {
              LastError = GetLastError();
              v7 = LastError;
              if ( LastError > 0 )
                v7 = (unsigned __int16)LastError | 0x80070000;
              goto LABEL_19;
            }
            if ( !CombineRgn(v12, v12, *((HRGN *)this + 141), 1) )
            {
LABEL_19:
              DeleteObject(v12);
              goto LABEL_20;
            }
            v14 = v12;
          }
          else
          {
            v14 = (HRGN)*((_QWORD *)this + 141);
          }
          ExtSelectClipRgn(a2, v14, 3);
          goto LABEL_19;
        }
      }
    }
  }
LABEL_20:
  if ( v7 >= 0 )
  {
    LOWORD(v20) = -1;
    CProxy_IInkOverlayEvents<CInkOverlay>::Fire_Painting((char *)this + 112, a2, v8, &v20);
    if ( (_WORD)v20 )
    {
      CInkAutoDataLock::CInkAutoDataLock(
        (CInkAutoDataLock *)&rect,
        (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
      if ( *((_WORD *)this + 193) == 0xFFFF )
      {
        v16 = (struct IInkRenderer *)v23;
        v7 = CInkOverlay::_DrawStrokes(this, a2, 0, *((_DWORD *)this + 99), 0, (struct IInkRenderer *)v23);
        if ( v7 >= 0 )
        {
          v17 = (struct IInkStrokes *)*((_QWORD *)this + 95);
          if ( v17 )
            v7 = CInkOverlay::_DrawStrokes(this, a2, v17, *((_DWORD *)this + 99), 1, v16);
        }
      }
      if ( v7 >= 0 )
      {
        if ( *((_DWORD *)this + 215) )
          CSelectionRect::RenderSingle((CInkOverlay *)((char *)this + 864), a2);
        if ( *((_DWORD *)this + 212) == 2 && *((_DWORD *)this + 235) == 1 )
        {
          v18 = *((_DWORD *)this + 156);
          if ( v18 )
          {
            if ( *((_DWORD *)this + 266) )
              v7 = CInkOverlay::_RenderLassoStroke(this, a2, v18, 0);
          }
        }
      }
      CInkAutoDataLock::Unlock((CInkAutoDataLock *)&rect);
      CProxy_IInkOverlayEvents<CInkOverlay>::Fire_Painted((char *)this + 112, a2, v8);
      CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&rect);
    }
  }
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v23);
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v21);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800df4d8  mov     [rsp-8+arg_18], rbx
0x1800df4dd  push    rbp
0x1800df4de  push    rsi
0x1800df4df  push    rdi
0x1800df4e0  push    r12
0x1800df4e2  push    r13
0x1800df4e4  push    r14
0x1800df4e6  push    r15
0x1800df4e8  lea     rbp, [rsp-27h]
0x1800df4ed  sub     rsp, 90h
0x1800df4f4  mov     rax, cs:__security_cookie
0x1800df4fb  xor     rax, rsp
0x1800df4fe  mov     [rbp+57h+var_40], rax
0x1800df502  mov     r15, r8
0x1800df505  mov     r14, rdx
0x1800df508  mov     rdi, rcx
0x1800df50b  xor     esi, esi
0x1800df50d  mov     [rbp+57h+var_90], esi
0x1800df510  xor     ebx, ebx
0x1800df512  mov     [rbp+57h+var_88], rbx
0x1800df516  mov     [rbp+57h+var_78], rbx
0x1800df51a  lea     rdx, [rcx+110h]; struct _RTL_CRITICAL_SECTION *
0x1800df521  lea     rcx, [rbp+57h+rect]; this
0x1800df525  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800df52a  nop
0x1800df52b  mov     r12d, [rdi+194h]
0x1800df532  mov     r13d, [rdi+350h]
0x1800df539  mov     eax, [rdi+444h]
0x1800df53f  mov     [rbp+57h+var_80], eax
0x1800df542  mov     rdx, [rdi+178h]; struct IUnknown *
0x1800df549  lea     rcx, [rbp+57h+var_78]; struct IUnknown **
0x1800df54d  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800df552  nop
0x1800df553  lea     rcx, [rbp+57h+rect]; this
0x1800df557  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800df55c  test    r15, r15
0x1800df55f  jnz     short loc_1800DF5B3
0x1800df561  xorps   xmm0, xmm0
0x1800df564  movups  xmmword ptr [rbp+57h+rect.left], xmm0
0x1800df568  lea     rdx, [rbp+57h+rect]; lprect
0x1800df56c  mov     rcx, r14; hdc
0x1800df56f  call    cs:__imp_GetClipBox
0x1800df575  movaps  xmm0, xmmword ptr [rbp+57h+rect.left]
0x1800df579  movdqa  xmmword ptr [rbp+57h+var_60.left], xmm0
0x1800df57e  lea     r8, [rbp+57h+var_90]; int *
0x1800df582  lea     rdx, [rbp+57h+var_60]; struct tagRECT
0x1800df586  lea     rcx, [rbp+57h+var_70]; this
0x1800df58a  call    ??0CIRect@@QEAA@UtagRECT@@AEAJ@Z; CIRect::CIRect(tagRECT,long &)
0x1800df58f  nop
0x1800df590  mov     esi, [rbp+57h+var_90]
0x1800df593  test    esi, esi
0x1800df595  js      short loc_1800DF5A8
0x1800df597  mov     rdx, [rbp+57h+var_70]; struct IUnknown *
0x1800df59b  lea     rcx, [rbp+57h+var_88]; struct IUnknown **
0x1800df59f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800df5a4  mov     rbx, [rbp+57h+var_88]
0x1800df5a8  lea     rcx, [rbp+57h+var_70]; void *
0x1800df5ac  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800df5b1  jmp     short loc_1800DF5C3
0x1800df5b3  mov     rdx, r15; struct IUnknown *
0x1800df5b6  lea     rcx, [rbp+57h+var_88]; struct IUnknown **
0x1800df5ba  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800df5bf  mov     rbx, [rbp+57h+var_88]
0x1800df5c3  test    r12d, r12d
0x1800df5c6  jz      loc_1800DF674
0x1800df5cc  cmp     r13d, 1
0x1800df5d0  jnz     loc_1800DF674
0x1800df5d6  xor     r13d, r13d
0x1800df5d9  cmp     [rbp+57h+var_80], 1
0x1800df5dd  jnz     loc_1800DF677
0x1800df5e3  cmp     [rdi+468h], r13
0x1800df5ea  jz      loc_1800DF677
0x1800df5f0  xor     r9d, r9d; y2
0x1800df5f3  xor     r8d, r8d; x2
0x1800df5f6  xor     edx, edx; y1
0x1800df5f8  xor     ecx, ecx; x1
0x1800df5fa  call    cs:__imp_CreateRectRgn
0x1800df600  mov     r15, rax
0x1800df603  test    rax, rax
0x1800df606  jz      short loc_1800DF677
0x1800df608  mov     rdx, rax; hrgn
0x1800df60b  mov     rcx, r14; hdc
0x1800df60e  call    cs:__imp_GetClipRgn
0x1800df614  test    eax, eax
0x1800df616  jnz     short loc_1800DF621
0x1800df618  mov     rdx, [rdi+468h]
0x1800df61f  jmp     short loc_1800DF643
0x1800df621  cmp     eax, 1
0x1800df624  jnz     short loc_1800DF654
0x1800df626  mov     r9d, eax; iMode
0x1800df629  mov     r8, [rdi+468h]; hrgnSrc2
0x1800df630  mov     rdx, r15; hrgnSrc1
0x1800df633  mov     rcx, r15; hrgnDst
0x1800df636  call    cs:__imp_CombineRgn
0x1800df63c  test    eax, eax
0x1800df63e  jz      short loc_1800DF669
0x1800df640  mov     rdx, r15; hrgn
0x1800df643  mov     r8d, 3; mode
0x1800df649  mov     rcx, r14; hdc
0x1800df64c  call    cs:__imp_ExtSelectClipRgn
0x1800df652  jmp     short loc_1800DF669
0x1800df654  call    cs:__imp_GetLastError
0x1800df65a  mov     esi, eax
0x1800df65c  test    eax, eax
0x1800df65e  jle     short loc_1800DF669
0x1800df660  movzx   esi, ax
0x1800df663  or      esi, 80070000h
0x1800df669  mov     rcx, r15; ho
0x1800df66c  call    cs:__imp_DeleteObject
0x1800df672  jmp     short loc_1800DF677
0x1800df674  xor     r13d, r13d
0x1800df677  test    esi, esi
0x1800df679  js      loc_1800DF78D
0x1800df67f  or      r15d, 0FFFFFFFFh
0x1800df683  mov     word ptr [rbp+57h+var_90], r15w
0x1800df688  lea     r9, [rbp+57h+var_90]
0x1800df68c  mov     r8, rbx
0x1800df68f  mov     rdx, r14
0x1800df692  lea     rcx, [rdi+70h]
0x1800df696  call    ?Fire_Painting@?$CProxy_IInkOverlayEvents@VCInkOverlay@@@@QEAAJ_JPEAUIInkRectangle@@PEAF@Z; CProxy_IInkOverlayEvents<CInkOverlay>::Fire_Painting(__int64,IInkRectangle *,short *)
0x1800df69b  cmp     word ptr [rbp+57h+var_90], r13w
0x1800df6a0  jz      loc_1800DF78D
0x1800df6a6  lea     rdx, [rdi+110h]; struct _RTL_CRITICAL_SECTION *
0x1800df6ad  lea     rcx, [rbp+57h+rect]; this
0x1800df6b1  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800df6b6  nop
0x1800df6b7  cmp     [rdi+182h], r15w
0x1800df6bf  jnz     short loc_1800DF717
0x1800df6c1  mov     r15, [rbp+57h+var_78]
0x1800df6c5  mov     [rsp+0C0h+var_98], r15; struct IInkRenderer *
0x1800df6ca  mov     [rsp+0C0h+var_A0], r13d; int
0x1800df6cf  mov     r9d, [rdi+18Ch]; int
0x1800df6d6  xor     r8d, r8d; struct IInkStrokes *
0x1800df6d9  mov     rdx, r14; HDC
0x1800df6dc  mov     rcx, rdi; this
0x1800df6df  call    ?_DrawStrokes@CInkOverlay@@AEAAJPEAUHDC__@@PEAUIInkStrokes@@HHPEAUIInkRenderer@@@Z; CInkOverlay::_DrawStrokes(HDC__ *,IInkStrokes *,int,int,IInkRenderer *)
0x1800df6e4  mov     esi, eax
0x1800df6e6  test    eax, eax
0x1800df6e8  js      short loc_1800DF717
0x1800df6ea  mov     r8, [rdi+2F8h]; struct IInkStrokes *
0x1800df6f1  test    r8, r8
0x1800df6f4  jz      short loc_1800DF717
0x1800df6f6  mov     [rsp+0C0h+var_98], r15; struct IInkRenderer *
0x1800df6fb  mov     [rsp+0C0h+var_A0], 1; int
0x1800df703  mov     r9d, [rdi+18Ch]; int
0x1800df70a  mov     rdx, r14; HDC
0x1800df70d  mov     rcx, rdi; this
0x1800df710  call    ?_DrawStrokes@CInkOverlay@@AEAAJPEAUHDC__@@PEAUIInkStrokes@@HHPEAUIInkRenderer@@@Z; CInkOverlay::_DrawStrokes(HDC__ *,IInkStrokes *,int,int,IInkRenderer *)
0x1800df715  mov     esi, eax
0x1800df717  test    esi, esi
0x1800df719  js      short loc_1800DF76A
0x1800df71b  cmp     [rdi+35Ch], r13d
0x1800df722  jz      short loc_1800DF733
0x1800df724  lea     rcx, [rdi+360h]; this
0x1800df72b  mov     rdx, r14; HDC
0x1800df72e  call    ?RenderSingle@CSelectionRect@@QEAAHPEAUHDC__@@@Z; CSelectionRect::RenderSingle(HDC__ *)
0x1800df733  cmp     dword ptr [rdi+350h], 2
0x1800df73a  jnz     short loc_1800DF76A
0x1800df73c  cmp     dword ptr [rdi+3ACh], 1
0x1800df743  jnz     short loc_1800DF76A
0x1800df745  mov     r8d, [rdi+270h]; unsigned int
0x1800df74c  test    r8d, r8d
0x1800df74f  jz      short loc_1800DF76A
0x1800df751  cmp     [rdi+428h], r13d
0x1800df758  jz      short loc_1800DF76A
0x1800df75a  xor     r9d, r9d; bool
0x1800df75d  mov     rdx, r14; HDC
0x1800df760  mov     rcx, rdi; this
0x1800df763  call    ?_RenderLassoStroke@CInkOverlay@@AEAAJPEAUHDC__@@K_N@Z; CInkOverlay::_RenderLassoStroke(HDC__ *,ulong,bool)
0x1800df768  mov     esi, eax
0x1800df76a  lea     rcx, [rbp+57h+rect]; this
0x1800df76e  call    ?Unlock@CInkAutoDataLock@@QEAAXXZ; CInkAutoDataLock::Unlock(void)
0x1800df773  mov     r8, rbx
0x1800df776  mov     rdx, r14
0x1800df779  lea     rcx, [rdi+70h]
0x1800df77d  call    ?Fire_Painted@?$CProxy_IInkOverlayEvents@VCInkOverlay@@@@QEAAJ_JPEAUIInkRectangle@@@Z; CProxy_IInkOverlayEvents<CInkOverlay>::Fire_Painted(__int64,IInkRectangle *)
0x1800df782  nop
0x1800df783  lea     rcx, [rbp+57h+rect]; this
0x1800df787  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800df78c  nop
0x1800df78d  lea     rcx, [rbp+57h+var_78]; void *
0x1800df791  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800df796  nop
0x1800df797  lea     rcx, [rbp+57h+var_88]; void *
0x1800df79b  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800df7a0  mov     eax, esi
0x1800df7a2  mov     rcx, [rbp+57h+var_40]
0x1800df7a6  xor     rcx, rsp; StackCookie
0x1800df7a9  call    __security_check_cookie
0x1800df7ae  mov     rbx, [rsp+0C0h+arg_18]
0x1800df7b6  add     rsp, 90h
0x1800df7bd  pop     r15
0x1800df7bf  pop     r14
0x1800df7c1  pop     r13
0x1800df7c3  pop     r12
0x1800df7c5  pop     rdi
0x1800df7c6  pop     rsi
0x1800df7c7  pop     rbp
0x1800df7c8  retn
```
