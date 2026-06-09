# CInkPicture::_DrawInk(HDC__ *,IInkRectangle *,IInkRenderer *)

- ea: `0x1800ef7e4`
- end: `0x1800efb00`
- name: `?_DrawInk@CInkPicture@@AEAAJPEAUHDC__@@PEAUIInkRectangle@@PEAUIInkRenderer@@@Z`
- size: `796`
- prototype: `__int64 __fastcall(CInkPicture *__hidden this, HDC, struct IInkRectangle *, struct IInkRenderer *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800eb9b0`

## callees

- `0x180001c20`
- `0x1800217b0`
- `0x1800276c4`
- `0x1800365f8`
- `0x180036824`
- `0x18003c5e4`
- `0x1800a6bf8`
- `0x1800e5478`
- `0x1800e98d0`
- `0x1800e997c`
- `0x1800ef7e4`
- `0x1800efb08`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef973`
- `GDI32!GetClipBox` at `0x1800ef88e`
- `GDI32!GetClipBox` at `0x1800ef88e`
- `GDI32!ExtSelectClipRgn` at `0x1800ef96b`
- `GDI32!ExtSelectClipRgn` at `0x1800ef96b`
- `GDI32!CombineRgn` at `0x1800ef955`
- `GDI32!CombineRgn` at `0x1800ef955`
- `GDI32!GetClipRgn` at `0x1800ef92d`
- `GDI32!GetClipRgn` at `0x1800ef92d`
- `GDI32!CreateRectRgn` at `0x1800ef919`
- `GDI32!CreateRectRgn` at `0x1800ef919`
- `GDI32!DeleteObject` at `0x1800ef98b`
- `GDI32!DeleteObject` at `0x1800ef98b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CInkPicture::_DrawInk(CInkPicture *this, HDC a2, struct IUnknown *a3, struct IInkRenderer *a4)
{
  int v8; // esi
  struct IUnknown *v9; // rbx
  int v10; // r13d
  struct IInkRenderer *v11; // rax
  HRGN RectRgn; // rax
  HRGN v13; // r15
  int ClipRgn; // eax
  HRGN v15; // rdx
  signed int LastError; // eax
  struct IInkRenderer *v17; // r13
  struct IInkStrokes *v18; // r8
  unsigned int v19; // r8d
  int v21; // [rsp+30h] [rbp-49h] BYREF
  struct IUnknown *v22; // [rsp+38h] [rbp-41h] BYREF
  int v23; // [rsp+40h] [rbp-39h]
  int v24; // [rsp+44h] [rbp-35h]
  struct IUnknown *v25; // [rsp+48h] [rbp-31h] BYREF
  struct IUnknown *v26; // [rsp+50h] [rbp-29h] BYREF
  struct IInkRenderer *v27; // [rsp+58h] [rbp-21h]
  struct tagRECT v28; // [rsp+60h] [rbp-19h] BYREF
  struct tagRECT rect; // [rsp+70h] [rbp-9h] BYREF

  v8 = 0;
  v21 = 0;
  v9 = 0;
  v22 = 0;
  v25 = 0;
  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)&rect, (struct _RTL_CRITICAL_SECTION *)((char *)this + 496));
  v10 = *((_DWORD *)this + 157);
  v23 = *((_DWORD *)this + 268);
  v24 = *((_DWORD *)this + 327);
  ATL::AtlComPtrAssign(&v25, *((struct IUnknown **)this + 75));
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&rect);
  v11 = a4;
  if ( !a4 )
    v11 = (struct IInkRenderer *)v25;
  v27 = v11;
  if ( a3 )
  {
    ATL::AtlComPtrAssign(&v22, a3);
    v9 = v22;
  }
  else
  {
    rect = 0;
    GetClipBox(a2, &rect);
    v28 = rect;
    CIRect::CIRect((CIRect *)&v26, &v28, &v21);
    v8 = v21;
    if ( v21 >= 0 )
    {
      ATL::AtlComPtrAssign(&v22, v26);
      v9 = v22;
    }
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v26);
  }
  if ( v10 )
  {
    if ( v23 == 1 && v24 == 1 )
    {
      if ( *((_QWORD *)this + 168) )
      {
        RectRgn = CreateRectRgn(0, 0, 0, 0);
        v13 = RectRgn;
        if ( RectRgn )
        {
          ClipRgn = GetClipRgn(a2, RectRgn);
          if ( ClipRgn )
          {
            if ( ClipRgn != 1 )
            {
              LastError = GetLastError();
              v8 = LastError;
              if ( LastError > 0 )
                v8 = (unsigned __int16)LastError | 0x80070000;
              goto LABEL_21;
            }
            if ( !CombineRgn(v13, v13, *((HRGN *)this + 168), 1) )
            {
LABEL_21:
              DeleteObject(v13);
              goto LABEL_22;
            }
            v15 = v13;
          }
          else
          {
            v15 = (HRGN)*((_QWORD *)this + 168);
          }
          ExtSelectClipRgn(a2, v15, 3);
          goto LABEL_21;
        }
      }
    }
  }
LABEL_22:
  if ( v8 >= 0 )
  {
    LOWORD(v21) = -1;
    CProxy_IInkPictureEvents<CInkPicture>::Fire_Painting((char *)this + 336, a2, v9, &v21);
    if ( (_WORD)v21 )
    {
      CInkAutoDataLock::CInkAutoDataLock(
        (CInkAutoDataLock *)&rect,
        (struct _RTL_CRITICAL_SECTION *)((char *)this + 496));
      if ( *((_WORD *)this + 305) == 0xFFFF )
      {
        v17 = v27;
        v8 = CInkPicture::_DrawStrokes(this, a2, 0, *((_DWORD *)this + 155), 0, v27);
        if ( v8 < 0 )
        {
LABEL_39:
          CInkAutoDataLock::Unlock((CInkAutoDataLock *)&rect);
          CProxy_IInkPictureEvents<CInkPicture>::Fire_Painted((char *)this + 336, a2, v9);
          CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)&rect);
          goto LABEL_40;
        }
        if ( !a4 )
        {
          v18 = (struct IInkStrokes *)*((_QWORD *)this + 123);
          if ( v18 )
            v8 = CInkPicture::_DrawStrokes(this, a2, v18, *((_DWORD *)this + 155), 1, v17);
        }
      }
      if ( v8 >= 0 )
      {
        if ( *((_DWORD *)this + 271) && !a4 )
          CSelectionRect::RenderSingle((CInkPicture *)((char *)this + 1088), a2);
        if ( *((_DWORD *)this + 268) == 2 && *((_DWORD *)this + 291) == 1 )
        {
          v19 = *((_DWORD *)this + 212);
          if ( v19 )
          {
            if ( *((_DWORD *)this + 320) && !a4 )
              v8 = CInkPicture::_RenderLassoStroke(this, a2, v19, 0);
          }
        }
      }
      goto LABEL_39;
    }
  }
LABEL_40:
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v25);
  ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800ef7e4  push    rbp
0x1800ef7e6  push    rbx
0x1800ef7e7  push    rsi
0x1800ef7e8  push    rdi
0x1800ef7e9  push    r12
0x1800ef7eb  push    r13
0x1800ef7ed  push    r14
0x1800ef7ef  push    r15
0x1800ef7f1  lea     rbp, [rsp-1Fh]
0x1800ef7f6  sub     rsp, 98h
0x1800ef7fd  mov     rax, cs:__security_cookie
0x1800ef804  xor     rax, rsp
0x1800ef807  mov     [rbp+57h+var_50], rax
0x1800ef80b  mov     r12, r9
0x1800ef80e  mov     r15, r8
0x1800ef811  mov     r14, rdx
0x1800ef814  mov     rdi, rcx
0x1800ef817  xor     eax, eax
0x1800ef819  mov     esi, eax
0x1800ef81b  mov     [rbp+57h+var_A0], eax
0x1800ef81e  mov     ebx, eax
0x1800ef820  mov     [rbp+57h+var_98], rax
0x1800ef824  mov     [rbp+57h+var_88], rax
0x1800ef828  lea     rdx, [rcx+1F0h]; struct _RTL_CRITICAL_SECTION *
0x1800ef82f  lea     rcx, [rbp+57h+rect]; this
0x1800ef833  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800ef838  nop
0x1800ef839  mov     r13d, [rdi+274h]
0x1800ef840  mov     eax, [rdi+430h]
0x1800ef846  mov     [rbp+57h+var_90], eax
0x1800ef849  mov     eax, [rdi+51Ch]
0x1800ef84f  mov     [rbp+57h+var_8C], eax
0x1800ef852  mov     rdx, [rdi+258h]; struct IUnknown *
0x1800ef859  lea     rcx, [rbp+57h+var_88]; struct IUnknown **
0x1800ef85d  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800ef862  nop
0x1800ef863  lea     rcx, [rbp+57h+rect]; this
0x1800ef867  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800ef86c  mov     rax, r12
0x1800ef86f  test    r12, r12
0x1800ef872  cmovz   rax, [rbp+57h+var_88]
0x1800ef877  mov     [rbp+57h+var_78], rax
0x1800ef87b  test    r15, r15
0x1800ef87e  jnz     short loc_1800EF8D2
0x1800ef880  xorps   xmm0, xmm0
0x1800ef883  movups  xmmword ptr [rbp+57h+rect.left], xmm0
0x1800ef887  lea     rdx, [rbp+57h+rect]; lprect
0x1800ef88b  mov     rcx, r14; hdc
0x1800ef88e  call    cs:__imp_GetClipBox
0x1800ef894  movaps  xmm0, xmmword ptr [rbp+57h+rect.left]
0x1800ef898  movdqa  xmmword ptr [rbp+57h+var_70.left], xmm0
0x1800ef89d  lea     r8, [rbp+57h+var_A0]; int *
0x1800ef8a1  lea     rdx, [rbp+57h+var_70]; struct tagRECT
0x1800ef8a5  lea     rcx, [rbp+57h+var_80]; this
0x1800ef8a9  call    ??0CIRect@@QEAA@UtagRECT@@AEAJ@Z; CIRect::CIRect(tagRECT,long &)
0x1800ef8ae  nop
0x1800ef8af  mov     esi, [rbp+57h+var_A0]
0x1800ef8b2  test    esi, esi
0x1800ef8b4  js      short loc_1800EF8C7
0x1800ef8b6  mov     rdx, [rbp+57h+var_80]; struct IUnknown *
0x1800ef8ba  lea     rcx, [rbp+57h+var_98]; struct IUnknown **
0x1800ef8be  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800ef8c3  mov     rbx, [rbp+57h+var_98]
0x1800ef8c7  lea     rcx, [rbp+57h+var_80]; void *
0x1800ef8cb  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800ef8d0  jmp     short loc_1800EF8E2
0x1800ef8d2  mov     rdx, r15; struct IUnknown *
0x1800ef8d5  lea     rcx, [rbp+57h+var_98]; struct IUnknown **
0x1800ef8d9  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800ef8de  mov     rbx, [rbp+57h+var_98]
0x1800ef8e2  test    r13d, r13d
0x1800ef8e5  jz      loc_1800EF993
0x1800ef8eb  xor     r13d, r13d
0x1800ef8ee  cmp     [rbp+57h+var_90], 1
0x1800ef8f2  jnz     loc_1800EF996
0x1800ef8f8  cmp     [rbp+57h+var_8C], 1
0x1800ef8fc  jnz     loc_1800EF996
0x1800ef902  cmp     [rdi+540h], r13
0x1800ef909  jz      loc_1800EF996
0x1800ef90f  xor     r9d, r9d; y2
0x1800ef912  xor     r8d, r8d; x2
0x1800ef915  xor     edx, edx; y1
0x1800ef917  xor     ecx, ecx; x1
0x1800ef919  call    cs:__imp_CreateRectRgn
0x1800ef91f  mov     r15, rax
0x1800ef922  test    rax, rax
0x1800ef925  jz      short loc_1800EF996
0x1800ef927  mov     rdx, rax; hrgn
0x1800ef92a  mov     rcx, r14; hdc
0x1800ef92d  call    cs:__imp_GetClipRgn
0x1800ef933  test    eax, eax
0x1800ef935  jnz     short loc_1800EF940
0x1800ef937  mov     rdx, [rdi+540h]
0x1800ef93e  jmp     short loc_1800EF962
0x1800ef940  cmp     eax, 1
0x1800ef943  jnz     short loc_1800EF973
0x1800ef945  mov     r9d, eax; iMode
0x1800ef948  mov     r8, [rdi+540h]; hrgnSrc2
0x1800ef94f  mov     rdx, r15; hrgnSrc1
0x1800ef952  mov     rcx, r15; hrgnDst
0x1800ef955  call    cs:__imp_CombineRgn
0x1800ef95b  test    eax, eax
0x1800ef95d  jz      short loc_1800EF988
0x1800ef95f  mov     rdx, r15; hrgn
0x1800ef962  mov     r8d, 3; mode
0x1800ef968  mov     rcx, r14; hdc
0x1800ef96b  call    cs:__imp_ExtSelectClipRgn
0x1800ef971  jmp     short loc_1800EF988
0x1800ef973  call    cs:__imp_GetLastError
0x1800ef979  mov     esi, eax
0x1800ef97b  test    eax, eax
0x1800ef97d  jle     short loc_1800EF988
0x1800ef97f  movzx   esi, ax
0x1800ef982  or      esi, 80070000h
0x1800ef988  mov     rcx, r15; ho
0x1800ef98b  call    cs:__imp_DeleteObject
0x1800ef991  jmp     short loc_1800EF996
0x1800ef993  xor     r13d, r13d
0x1800ef996  test    esi, esi
0x1800ef998  js      loc_1800EFACB
0x1800ef99e  or      eax, 0FFFFFFFFh
0x1800ef9a1  mov     word ptr [rbp+57h+var_A0], ax
0x1800ef9a5  lea     r15, [rdi+150h]
0x1800ef9ac  lea     r9, [rbp+57h+var_A0]
0x1800ef9b0  mov     r8, rbx
0x1800ef9b3  mov     rdx, r14
0x1800ef9b6  mov     rcx, r15
0x1800ef9b9  call    ?Fire_Painting@?$CProxy_IInkPictureEvents@VCInkPicture@@@@QEAAJ_JPEAUIInkRectangle@@PEAF@Z; CProxy_IInkPictureEvents<CInkPicture>::Fire_Painting(__int64,IInkRectangle *,short *)
0x1800ef9be  cmp     word ptr [rbp+57h+var_A0], r13w
0x1800ef9c3  jz      loc_1800EFACB
0x1800ef9c9  lea     rdx, [rdi+1F0h]; struct _RTL_CRITICAL_SECTION *
0x1800ef9d0  lea     rcx, [rbp+57h+rect]; this
0x1800ef9d4  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800ef9d9  nop
0x1800ef9da  or      eax, 0FFFFFFFFh
0x1800ef9dd  cmp     [rdi+262h], ax
0x1800ef9e4  jnz     short loc_1800EFA4A
0x1800ef9e6  mov     r13, [rbp+57h+var_78]
0x1800ef9ea  mov     [rsp+0D0h+var_A8], r13; struct IInkRenderer *
0x1800ef9ef  mov     [rsp+0D0h+var_B0], 0; int
0x1800ef9f7  mov     r9d, [rdi+26Ch]; int
0x1800ef9fe  xor     r8d, r8d; struct IInkStrokes *
0x1800efa01  mov     rdx, r14; HDC
0x1800efa04  mov     rcx, rdi; this
0x1800efa07  call    ?_DrawStrokes@CInkPicture@@AEAAJPEAUHDC__@@PEAUIInkStrokes@@HHPEAUIInkRenderer@@@Z; CInkPicture::_DrawStrokes(HDC__ *,IInkStrokes *,int,int,IInkRenderer *)
0x1800efa0c  mov     esi, eax
0x1800efa0e  xor     eax, eax
0x1800efa10  test    esi, esi
0x1800efa12  js      loc_1800EFAA9
0x1800efa18  test    r12, r12
0x1800efa1b  jnz     short loc_1800EFA4C
0x1800efa1d  mov     r8, [rdi+3D8h]; struct IInkStrokes *
0x1800efa24  test    r8, r8
0x1800efa27  jz      short loc_1800EFA4C
0x1800efa29  mov     [rsp+0D0h+var_A8], r13; struct IInkRenderer *
0x1800efa2e  mov     [rsp+0D0h+var_B0], 1; int
0x1800efa36  mov     r9d, [rdi+26Ch]; int
0x1800efa3d  mov     rdx, r14; HDC
0x1800efa40  mov     rcx, rdi; this
0x1800efa43  call    ?_DrawStrokes@CInkPicture@@AEAAJPEAUHDC__@@PEAUIInkStrokes@@HHPEAUIInkRenderer@@@Z; CInkPicture::_DrawStrokes(HDC__ *,IInkStrokes *,int,int,IInkRenderer *)
0x1800efa48  mov     esi, eax
0x1800efa4a  xor     eax, eax
0x1800efa4c  test    esi, esi
0x1800efa4e  js      short loc_1800EFAA9
0x1800efa50  cmp     [rdi+43Ch], eax
0x1800efa56  jz      short loc_1800EFA6E
0x1800efa58  test    r12, r12
0x1800efa5b  jnz     short loc_1800EFA6E
0x1800efa5d  lea     rcx, [rdi+440h]; this
0x1800efa64  mov     rdx, r14; HDC
0x1800efa67  call    ?RenderSingle@CSelectionRect@@QEAAHPEAUHDC__@@@Z; CSelectionRect::RenderSingle(HDC__ *)
0x1800efa6c  xor     eax, eax
0x1800efa6e  cmp     dword ptr [rdi+430h], 2
0x1800efa75  jnz     short loc_1800EFAA9
0x1800efa77  cmp     dword ptr [rdi+48Ch], 1
0x1800efa7e  jnz     short loc_1800EFAA9
0x1800efa80  mov     r8d, [rdi+350h]; unsigned int
0x1800efa87  test    r8d, r8d
0x1800efa8a  jz      short loc_1800EFAA9
0x1800efa8c  cmp     [rdi+500h], eax
0x1800efa92  jz      short loc_1800EFAA9
0x1800efa94  test    r12, r12
0x1800efa97  jnz     short loc_1800EFAA9
0x1800efa99  xor     r9d, r9d; bool
0x1800efa9c  mov     rdx, r14; HDC
0x1800efa9f  mov     rcx, rdi; this
0x1800efaa2  call    ?_RenderLassoStroke@CInkPicture@@AEAAJPEAUHDC__@@K_N@Z; CInkPicture::_RenderLassoStroke(HDC__ *,ulong,bool)
0x1800efaa7  mov     esi, eax
0x1800efaa9  lea     rcx, [rbp+57h+rect]; this
0x1800efaad  call    ?Unlock@CInkAutoDataLock@@QEAAXXZ; CInkAutoDataLock::Unlock(void)
0x1800efab2  mov     r8, rbx
0x1800efab5  mov     rdx, r14
0x1800efab8  mov     rcx, r15
0x1800efabb  call    ?Fire_Painted@?$CProxy_IInkPictureEvents@VCInkPicture@@@@QEAAJ_JPEAUIInkRectangle@@@Z; CProxy_IInkPictureEvents<CInkPicture>::Fire_Painted(__int64,IInkRectangle *)
0x1800efac0  nop
0x1800efac1  lea     rcx, [rbp+57h+rect]; this
0x1800efac5  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800efaca  nop
0x1800efacb  lea     rcx, [rbp+57h+var_88]; void *
0x1800efacf  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800efad4  nop
0x1800efad5  lea     rcx, [rbp+57h+var_98]; void *
0x1800efad9  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800efade  mov     eax, esi
0x1800efae0  mov     rcx, [rbp+57h+var_50]
0x1800efae4  xor     rcx, rsp; StackCookie
0x1800efae7  call    __security_check_cookie
0x1800efaec  add     rsp, 98h
0x1800efaf3  pop     r15
0x1800efaf5  pop     r14
0x1800efaf7  pop     r13
0x1800efaf9  pop     r12
0x1800efafb  pop     rdi
0x1800efafc  pop     rsi
0x1800efafd  pop     rbx
0x1800efafe  pop     rbp
0x1800efaff  retn
```
