# CDC::DrawDragRect(tagRECT const *,tagSIZE,tagRECT const *,tagSIZE,CBrush *,CBrush *)

- ea: `0x18005eb20`
- end: `0x18005ee55`
- name: `?DrawDragRect@CDC@@QEAAXPEBUtagRECT@@UtagSIZE@@01PEAVCBrush@@2@Z`
- size: `821`
- prototype: `void __usercall(CDC *__hidden this@<rcx>, RECT *lprcSrc2@<rdx>, struct tagSIZE@<r8>, const struct tagRECT *@<r9>, struct tagSIZE, struct CBrush *, struct CBrush *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18004aef0`
- `0x180050240`

## callees

- `0x18000e790`
- `0x180052850`
- `0x18005e0b0`
- `0x18005e1e0`
- `0x18005ea10`
- `0x18005eb20`
- `0x18005ee60`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!IntersectRect` at `0x18005ebb7`
- `USER32!IntersectRect` at `0x18005ec8e`
- `USER32!IntersectRect` at `0x18005ebb7`
- `USER32!IntersectRect` at `0x18005ec8e`
- `USER32!CopyRect` at `0x18005eb93`
- `USER32!CopyRect` at `0x18005ec67`
- `USER32!CopyRect` at `0x18005eb93`
- `USER32!CopyRect` at `0x18005ec67`
- `USER32!InflateRect` at `0x18005eba6`
- `USER32!InflateRect` at `0x18005ec7d`
- `USER32!InflateRect` at `0x18005eba6`
- `USER32!InflateRect` at `0x18005ec7d`
- `GDI32!PatBlt` at `0x18005ed5e`
- `GDI32!PatBlt` at `0x18005edcf`
- `GDI32!PatBlt` at `0x18005ed5e`
- `GDI32!PatBlt` at `0x18005edcf`
- `GDI32!CombineRgn` at `0x18005ebf3`
- `GDI32!CombineRgn` at `0x18005ecbf`
- `GDI32!CombineRgn` at `0x18005ecf4`
- `GDI32!CombineRgn` at `0x18005ebf3`
- `GDI32!CombineRgn` at `0x18005ecbf`
- `GDI32!CombineRgn` at `0x18005ecf4`
- `GDI32!SetRectRgn` at `0x18005ec5a`
- `GDI32!SetRectRgn` at `0x18005ecaa`
- `GDI32!SetRectRgn` at `0x18005ec5a`
- `GDI32!SetRectRgn` at `0x18005ecaa`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CDC::DrawDragRect(
        HDC *this,
        RECT *lprcSrc2,
        struct tagSIZE a3,
        const struct tagRECT *a4,
        struct tagSIZE a5,
        struct CBrush *a6,
        struct CBrush *a7)
{
  LONG cx; // ebx
  LONG cy; // edi
  struct CBrush *HalftoneBrush; // r12
  struct CBrush *v13; // r15
  struct CPen *v14; // rbx
  void ***v15; // rdx
  struct CPen *v16; // rbx
  void **v17; // [rsp+30h] [rbp-71h] BYREF
  HRGN v18; // [rsp+38h] [rbp-69h]
  void **v19; // [rsp+40h] [rbp-61h] BYREF
  HRGN v20; // [rsp+48h] [rbp-59h]
  void **v21; // [rsp+50h] [rbp-51h] BYREF
  HRGN hrgnSrc2; // [rsp+58h] [rbp-49h]
  void **v23; // [rsp+60h] [rbp-41h] BYREF
  HRGN hrgnSrc1; // [rsp+68h] [rbp-39h]
  void **v25; // [rsp+70h] [rbp-31h] BYREF
  HRGN hrgnDst; // [rsp+78h] [rbp-29h]
  struct tagRECT rcDst; // [rsp+80h] [rbp-21h] BYREF

  cx = a3.cx;
  cy = a3.cy;
  HalftoneBrush = a6;
  v13 = a7;
  hrgnDst = 0;
  v25 = &CRgn::`vftable';
  hrgnSrc1 = 0;
  v23 = &CRgn::`vftable';
  hrgnSrc2 = 0;
  v21 = &CRgn::`vftable';
  CRgn::CreateRectRgnIndirect((CRgn *)&v23, lprcSrc2);
  CopyRect(&rcDst, lprcSrc2);
  InflateRect(&rcDst, -cx, -cy);
  IntersectRect(&rcDst, &rcDst, lprcSrc2);
  CRgn::CreateRectRgnIndirect((CRgn *)&v21, &rcDst);
  CRgn::CreateRectRgn((CRgn *)&v25, 0, 0, 0, 0);
  CombineRgn(hrgnDst, hrgnSrc1, hrgnSrc2, 3);
  if ( !a6 )
    HalftoneBrush = CDC::GetHalftoneBrush();
  if ( !a7 )
    v13 = HalftoneBrush;
  v20 = 0;
  v19 = &CRgn::`vftable';
  v18 = 0;
  v17 = &CRgn::`vftable';
  if ( a4 )
  {
    CRgn::CreateRectRgn((CRgn *)&v19, 0, 0, 0, 0);
    SetRectRgn(hrgnSrc1, a4->left, a4->top, a4->right, a4->bottom);
    CopyRect(&rcDst, a4);
    InflateRect(&rcDst, -a5.cx, -a5.cy);
    IntersectRect(&rcDst, &rcDst, a4);
    SetRectRgn(hrgnSrc2, rcDst.left, rcDst.top, rcDst.right, rcDst.bottom);
    CombineRgn(v20, hrgnSrc1, hrgnSrc2, 3);
    if ( *((_QWORD *)HalftoneBrush + 1) == *((_QWORD *)v13 + 1) )
    {
      CRgn::CreateRectRgn((CRgn *)&v17, 0, 0, 0, 0);
      CombineRgn(v18, v20, hrgnDst, 3);
    }
  }
  if ( *((_QWORD *)HalftoneBrush + 1) != *((_QWORD *)v13 + 1) && a4 )
  {
    CDC::SelectClipRgn((CDC *)this, (struct CRgn *)&v19);
    (*((void (__fastcall **)(HDC *, struct tagRECT *))*this + 22))(this, &rcDst);
    v14 = CDC::SelectObject((CDC *)this, v13);
    PatBlt(this[1], rcDst.left, rcDst.top, rcDst.right - rcDst.left, rcDst.bottom - rcDst.top, 0x5A0049u);
    CDC::SelectObject((CDC *)this, v14);
  }
  v15 = &v17;
  if ( !v18 )
    v15 = &v25;
  CDC::SelectClipRgn((CDC *)this, (struct CRgn *)v15);
  (*((void (__fastcall **)(HDC *, struct tagRECT *))*this + 22))(this, &rcDst);
  v16 = CDC::SelectObject((CDC *)this, HalftoneBrush);
  PatBlt(this[1], rcDst.left, rcDst.top, rcDst.right - rcDst.left, rcDst.bottom - rcDst.top, 0x5A0049u);
  if ( v16 )
    CDC::SelectObject((CDC *)this, v16);
  CDC::SelectClipRgn((CDC *)this, 0);
  v17 = &CRgn::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&v17);
  v19 = &CRgn::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&v19);
  v21 = &CRgn::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&v21);
  v23 = &CRgn::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&v23);
  v25 = &CRgn::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&v25);
}

```

## disassembly

```asm
0x18005eb20  push    rbp
0x18005eb22  push    rbx
0x18005eb23  push    rsi
0x18005eb24  push    rdi
0x18005eb25  push    r12
0x18005eb27  push    r13
0x18005eb29  push    r14
0x18005eb2b  push    r15
0x18005eb2d  lea     rbp, [rsp-7]
0x18005eb32  sub     rsp, 0A8h
0x18005eb39  mov     rax, cs:__security_cookie
0x18005eb40  xor     rax, rsp
0x18005eb43  mov     [rbp+3Fh+var_50], rax
0x18005eb47  mov     r13, r9
0x18005eb4a  mov     rbx, r8
0x18005eb4d  mov     rsi, rdx
0x18005eb50  mov     r14, rcx
0x18005eb53  mov     rdi, r8
0x18005eb56  shr     rdi, 20h
0x18005eb5a  mov     r12, [rbp+3Fh+arg_28]
0x18005eb5e  mov     r15, [rbp+3Fh+arg_30]
0x18005eb62  xor     eax, eax
0x18005eb64  mov     [rbp+3Fh+hrgnDst], rax
0x18005eb68  lea     rcx, ??_7CRgn@@6B@; const CRgn::`vftable'
0x18005eb6f  mov     [rbp+3Fh+var_70], rcx
0x18005eb73  mov     [rbp+3Fh+hrgnSrc1], rax
0x18005eb77  mov     [rbp+3Fh+var_80], rcx
0x18005eb7b  mov     [rbp+3Fh+hrgnSrc2], rax
0x18005eb7f  mov     [rbp+3Fh+var_90], rcx
0x18005eb83  lea     rcx, [rbp+3Fh+var_80]; this
0x18005eb87  call    ?CreateRectRgnIndirect@CRgn@@QEAAHPEBUtagRECT@@@Z; CRgn::CreateRectRgnIndirect(tagRECT const *)
0x18005eb8c  mov     rdx, rsi; lprcSrc
0x18005eb8f  lea     rcx, [rbp+3Fh+rcDst]; lprcDst
0x18005eb93  call    cs:__imp_CopyRect
0x18005eb99  neg     edi
0x18005eb9b  neg     ebx
0x18005eb9d  mov     r8d, edi; dy
0x18005eba0  mov     edx, ebx; dx
0x18005eba2  lea     rcx, [rbp+3Fh+rcDst]; lprc
0x18005eba6  call    cs:__imp_InflateRect
0x18005ebac  mov     r8, rsi; lprcSrc2
0x18005ebaf  lea     rdx, [rbp+3Fh+rcDst]; lprcSrc1
0x18005ebb3  lea     rcx, [rbp+3Fh+rcDst]; lprcDst
0x18005ebb7  call    cs:__imp_IntersectRect
0x18005ebbd  lea     rdx, [rbp+3Fh+rcDst]; lprect
0x18005ebc1  lea     rcx, [rbp+3Fh+var_90]; this
0x18005ebc5  call    ?CreateRectRgnIndirect@CRgn@@QEAAHPEBUtagRECT@@@Z; CRgn::CreateRectRgnIndirect(tagRECT const *)
0x18005ebca  xor     edi, edi
0x18005ebcc  mov     [rsp+0E0h+bottom], edi; y2
0x18005ebd0  xor     r9d, r9d; x2
0x18005ebd3  xor     r8d, r8d; y1
0x18005ebd6  xor     edx, edx; x1
0x18005ebd8  lea     rcx, [rbp+3Fh+var_70]; this
0x18005ebdc  call    ?CreateRectRgn@CRgn@@QEAAHHHHH@Z; CRgn::CreateRectRgn(int,int,int,int)
0x18005ebe1  lea     ebx, [rdi+3]
0x18005ebe4  mov     r9d, ebx; iMode
0x18005ebe7  mov     r8, [rbp+3Fh+hrgnSrc2]; hrgnSrc2
0x18005ebeb  mov     rdx, [rbp+3Fh+hrgnSrc1]; hrgnSrc1
0x18005ebef  mov     rcx, [rbp+3Fh+hrgnDst]; hrgnDst
0x18005ebf3  call    cs:__imp_CombineRgn
0x18005ebf9  test    r12, r12
0x18005ebfc  jnz     short loc_18005EC06
0x18005ebfe  call    ?GetHalftoneBrush@CDC@@SAPEAVCBrush@@XZ; CDC::GetHalftoneBrush(void)
0x18005ec03  mov     r12, rax
0x18005ec06  test    r15, r15
0x18005ec09  cmovz   r15, r12
0x18005ec0d  mov     [rbp+3Fh+var_98], rdi
0x18005ec11  lea     rsi, ??_7CRgn@@6B@; const CRgn::`vftable'
0x18005ec18  mov     [rbp+3Fh+var_A0], rsi
0x18005ec1c  mov     [rbp+3Fh+var_A8], rdi
0x18005ec20  mov     [rbp+3Fh+var_B0], rsi
0x18005ec24  test    r13, r13
0x18005ec27  jz      loc_18005ECFA
0x18005ec2d  mov     [rsp+0E0h+bottom], edi; y2
0x18005ec31  xor     r9d, r9d; x2
0x18005ec34  xor     r8d, r8d; y1
0x18005ec37  xor     edx, edx; x1
0x18005ec39  lea     rcx, [rbp+3Fh+var_A0]; this
0x18005ec3d  call    ?CreateRectRgn@CRgn@@QEAAHHHHH@Z; CRgn::CreateRectRgn(int,int,int,int)
0x18005ec42  mov     eax, [r13+0Ch]
0x18005ec46  mov     [rsp+0E0h+bottom], eax; bottom
0x18005ec4a  mov     r9d, [r13+8]; right
0x18005ec4e  mov     r8d, [r13+4]; top
0x18005ec52  mov     edx, [r13+0]; left
0x18005ec56  mov     rcx, [rbp+3Fh+hrgnSrc1]; hrgn
0x18005ec5a  call    cs:__imp_SetRectRgn
0x18005ec60  mov     rdx, r13; lprcSrc
0x18005ec63  lea     rcx, [rbp+3Fh+rcDst]; lprcDst
0x18005ec67  call    cs:__imp_CopyRect
0x18005ec6d  mov     r8d, [rbp+3Fh+arg_20.cy]
0x18005ec71  neg     r8d; dy
0x18005ec74  mov     edx, [rbp+3Fh+arg_20.cx]
0x18005ec77  neg     edx; dx
0x18005ec79  lea     rcx, [rbp+3Fh+rcDst]; lprc
0x18005ec7d  call    cs:__imp_InflateRect
0x18005ec83  mov     r8, r13; lprcSrc2
0x18005ec86  lea     rdx, [rbp+3Fh+rcDst]; lprcSrc1
0x18005ec8a  lea     rcx, [rbp+3Fh+rcDst]; lprcDst
0x18005ec8e  call    cs:__imp_IntersectRect
0x18005ec94  mov     eax, [rbp+3Fh+rcDst.bottom]
0x18005ec97  mov     [rsp+0E0h+bottom], eax; bottom
0x18005ec9b  mov     r9d, [rbp+3Fh+rcDst.right]; right
0x18005ec9f  mov     r8d, [rbp+3Fh+rcDst.top]; top
0x18005eca3  mov     edx, [rbp+3Fh+rcDst.left]; left
0x18005eca6  mov     rcx, [rbp+3Fh+hrgnSrc2]; hrgn
0x18005ecaa  call    cs:__imp_SetRectRgn
0x18005ecb0  mov     r9d, ebx; iMode
0x18005ecb3  mov     r8, [rbp+3Fh+hrgnSrc2]; hrgnSrc2
0x18005ecb7  mov     rdx, [rbp+3Fh+hrgnSrc1]; hrgnSrc1
0x18005ecbb  mov     rcx, [rbp+3Fh+var_98]; hrgnDst
0x18005ecbf  call    cs:__imp_CombineRgn
0x18005ecc5  mov     rax, [r15+8]
0x18005ecc9  cmp     [r12+8], rax
0x18005ecce  jnz     short loc_18005ECFA
0x18005ecd0  mov     [rsp+0E0h+bottom], edi; y2
0x18005ecd4  xor     r9d, r9d; x2
0x18005ecd7  xor     r8d, r8d; y1
0x18005ecda  xor     edx, edx; x1
0x18005ecdc  lea     rcx, [rbp+3Fh+var_B0]; this
0x18005ece0  call    ?CreateRectRgn@CRgn@@QEAAHHHHH@Z; CRgn::CreateRectRgn(int,int,int,int)
0x18005ece5  mov     r9d, ebx; iMode
0x18005ece8  mov     r8, [rbp+3Fh+hrgnDst]; hrgnSrc2
0x18005ecec  mov     rdx, [rbp+3Fh+var_98]; hrgnSrc1
0x18005ecf0  mov     rcx, [rbp+3Fh+var_A8]; hrgnDst
0x18005ecf4  call    cs:__imp_CombineRgn
0x18005ecfa  mov     rax, [r15+8]
0x18005ecfe  cmp     [r12+8], rax
0x18005ed03  jz      short loc_18005ED6F
0x18005ed05  test    r13, r13
0x18005ed08  jz      short loc_18005ED6F
0x18005ed0a  lea     rdx, [rbp+3Fh+var_A0]; struct CRgn *
0x18005ed0e  mov     rcx, r14; this
0x18005ed11  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x18005ed16  mov     rax, [r14]
0x18005ed19  lea     rdx, [rbp+3Fh+rcDst]
0x18005ed1d  mov     rcx, r14
0x18005ed20  mov     rax, [rax+0B0h]
0x18005ed27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed2c  mov     rdx, r15; struct CPen *
0x18005ed2f  mov     rcx, r14; this
0x18005ed32  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18005ed37  mov     rbx, rax
0x18005ed3a  mov     ecx, [rbp+3Fh+rcDst.bottom]
0x18005ed3d  mov     r8d, [rbp+3Fh+rcDst.top]; y
0x18005ed41  sub     ecx, r8d
0x18005ed44  mov     r9d, [rbp+3Fh+rcDst.right]
0x18005ed48  mov     edx, [rbp+3Fh+rcDst.left]; x
0x18005ed4b  sub     r9d, edx; w
0x18005ed4e  mov     [rsp+0E0h+rop], 5A0049h; rop
0x18005ed56  mov     [rsp+0E0h+bottom], ecx; h
0x18005ed5a  mov     rcx, [r14+8]; hdc
0x18005ed5e  call    cs:__imp_PatBlt
0x18005ed64  mov     rdx, rbx; struct CPen *
0x18005ed67  mov     rcx, r14; this
0x18005ed6a  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18005ed6f  lea     rdx, [rbp+3Fh+var_B0]
0x18005ed73  lea     rax, [rbp+3Fh+var_70]
0x18005ed77  cmp     [rbp+3Fh+var_A8], rdi
0x18005ed7b  cmovz   rdx, rax; struct CRgn *
0x18005ed7f  mov     rcx, r14; this
0x18005ed82  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x18005ed87  mov     rax, [r14]
0x18005ed8a  lea     rdx, [rbp+3Fh+rcDst]
0x18005ed8e  mov     rcx, r14
0x18005ed91  mov     rax, [rax+0B0h]
0x18005ed98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed9d  mov     rdx, r12; struct CPen *
0x18005eda0  mov     rcx, r14; this
0x18005eda3  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18005eda8  mov     rbx, rax
0x18005edab  mov     ecx, [rbp+3Fh+rcDst.bottom]
0x18005edae  mov     r8d, [rbp+3Fh+rcDst.top]; y
0x18005edb2  sub     ecx, r8d
0x18005edb5  mov     r9d, [rbp+3Fh+rcDst.right]
0x18005edb9  mov     edx, [rbp+3Fh+rcDst.left]; x
0x18005edbc  sub     r9d, edx; w
0x18005edbf  mov     [rsp+0E0h+rop], 5A0049h; rop
0x18005edc7  mov     [rsp+0E0h+bottom], ecx; h
0x18005edcb  mov     rcx, [r14+8]; hdc
0x18005edcf  call    cs:__imp_PatBlt
0x18005edd5  test    rbx, rbx
0x18005edd8  jz      short loc_18005EDE5
0x18005edda  mov     rdx, rbx; struct CPen *
0x18005eddd  mov     rcx, r14; this
0x18005ede0  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18005ede5  xor     edx, edx; struct CRgn *
0x18005ede7  mov     rcx, r14; this
0x18005edea  call    ?SelectClipRgn@CDC@@QEAAHPEAVCRgn@@@Z; CDC::SelectClipRgn(CRgn *)
0x18005edef  nop
0x18005edf0  mov     [rbp+3Fh+var_B0], rsi
0x18005edf4  lea     rcx, [rbp+3Fh+var_B0]; this
0x18005edf8  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005edfd  nop
0x18005edfe  mov     [rbp+3Fh+var_A0], rsi
0x18005ee02  lea     rcx, [rbp+3Fh+var_A0]; this
0x18005ee06  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005ee0b  nop
0x18005ee0c  mov     [rbp+3Fh+var_90], rsi
0x18005ee10  lea     rcx, [rbp+3Fh+var_90]; this
0x18005ee14  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005ee19  nop
0x18005ee1a  mov     [rbp+3Fh+var_80], rsi
0x18005ee1e  lea     rcx, [rbp+3Fh+var_80]; this
0x18005ee22  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005ee27  nop
0x18005ee28  mov     [rbp+3Fh+var_70], rsi
0x18005ee2c  lea     rcx, [rbp+3Fh+var_70]; this
0x18005ee30  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005ee35  mov     rcx, [rbp+3Fh+var_50]
0x18005ee39  xor     rcx, rsp; StackCookie
0x18005ee3c  call    __security_check_cookie
0x18005ee41  add     rsp, 0A8h
0x18005ee48  pop     r15
0x18005ee4a  pop     r14
0x18005ee4c  pop     r13
0x18005ee4e  pop     r12
0x18005ee50  pop     rdi
0x18005ee51  pop     rsi
0x18005ee52  pop     rbx
0x18005ee53  pop     rbp
0x18005ee54  retn
```
