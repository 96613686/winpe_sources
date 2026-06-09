# CRenderer::RenderOutlineSymbol(void)

- ea: `0x180137be8`
- end: `0x180137e7f`
- name: `?RenderOutlineSymbol@CRenderer@@QEAAHXZ`
- size: `663`
- prototype: `__int64 __fastcall(CRenderer *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18005a840`

## callees

- `0x18001dbc0`
- `0x1800219c8`
- `0x18002357c`
- `0x18003211c`
- `0x180034060`
- `0x18008db68`
- `0x1800e4124`
- `0x18011171c`
- `0x180121460`
- `0x180137be8`
- `0x180137e88`
- `0x18014d298`
- `0x1801679f0`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180137e62`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180137e62`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180137c6e`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180137c6e`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180137d7d`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180137e59`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180137d7d`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180137e59`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x180137e4d`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x180137e4d`

## pseudocode

```c
__int64 __fastcall CRenderer::RenderOutlineSymbol(CRenderer *this)
{
  const struct CParaFormat *PF; // rax
  int v3; // eax
  LONG v4; // ecx
  HDC v5; // rax
  HDC hdcSrc; // r12
  const struct CParaFormat *v8; // rax
  unsigned int v9; // r15d
  HGDIOBJ v10; // rdi
  int v11; // ebx
  int CchLeft; // eax
  int EOP; // r11d
  __int64 v14; // xmm1_8
  __int128 v15; // xmm0
  const struct CParaFormat *v16; // rax
  int v17; // ebx
  bool v18; // cc
  HGDIOBJ v19; // rsi
  int hDest; // edi
  int Ascent; // eax
  int v22; // r8d
  int v23; // ecx
  int v24; // eax
  CDisplay *v25; // rcx
  int v26; // ebx
  HDC v27; // rax
  int v28; // [rsp+60h] [rbp-39h]
  _BYTE v29[24]; // [rsp+68h] [rbp-31h] BYREF
  __int128 v30; // [rsp+80h] [rbp-19h] BYREF
  __int64 v31; // [rsp+90h] [rbp-9h]
  __int128 v32; // [rsp+98h] [rbp-1h]
  int wSrc; // [rsp+100h] [rbp+67h]
  struct tagPOINT xDest; // [rsp+108h] [rbp+6Fh] BYREF
  int v35; // [rsp+110h] [rbp+77h] BYREF
  int v36; // [rsp+114h] [rbp+7Bh]
  int v37; // [rsp+118h] [rbp+7Fh]

  PF = (const struct CParaFormat *)*((_QWORD *)this + 37);
  if ( !PF )
    PF = CRchTxtPtr::GetPF(this);
  v3 = CMeasurerNoFC::LUtoDUZ(this, 360 * (unsigned int)*((unsigned __int8 *)PF + 35));
  v4 = *((_DWORD *)this + 128);
  v37 = v3;
  v35 = *((_DWORD *)this + 25);
  v28 = *((_DWORD *)this + 129);
  xDest.x = v4;
  if ( !h && (unsigned int)InitializeOutlineBitmaps() )
    return 0;
  v5 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
  hdcSrc = CreateCompatibleDC(v5);
  if ( !hdcSrc )
    return 0;
  v8 = (const struct CParaFormat *)*((_QWORD *)this + 37);
  if ( !v8 )
    v8 = CRchTxtPtr::GetPF(this);
  v9 = 1;
  if ( (*((_BYTE *)v8 + 35) & 1) != 0 )
  {
    v10 = h;
    v11 = 4;
    wSrc = 4;
  }
  else
  {
    v10 = (HGDIOBJ)qword_1802DF568;
    v11 = 10;
    wSrc = 10;
    CPFRunPtr::CPFRunPtr((CPFRunPtr *)v29, this);
    CchLeft = CRunPtrBase::GetCchLeft((CRunPtrBase *)v29);
    if ( EOP < CchLeft )
    {
      v14 = *((_QWORD *)this + 4);
      v30 = *((_OWORD *)this + 1);
      v15 = *(_OWORD *)((char *)this + 40);
      v31 = v14;
      v32 = v15;
      EOP = CTxtPtrEx::FindEOP((CTxtPtrEx *)&v30, 0x3FFFFFFF, 0, 0);
    }
    CRunPtrBase::Move((CRunPtrBase *)v29, EOP);
    if ( (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)v29) )
    {
      v10 = qword_1802DF570;
    }
    else
    {
      v16 = (const struct CParaFormat *)*((_QWORD *)this + 37);
      if ( !v16 )
        v16 = CRchTxtPtr::GetPF(this);
      v17 = *((unsigned __int8 *)v16 + 35);
      v18 = v17 < (int)CPFRunPtr::GetOutlineLevel((CPFRunPtr *)v29);
      v11 = 10;
      if ( v18 )
        v10 = qword_1802DF578;
    }
  }
  if ( v10 )
  {
    v19 = SelectObject(hdcSrc, v10);
    hDest = CDisplay::Zoom(*((CDisplay **)this + 19), v11);
    Ascent = CLine::GetAscent((CRenderer *)((char *)this + 96), 0, 0);
    v22 = Ascent - hDest;
    v23 = hDest - Ascent;
    v35 = v37 + xDest.x - v35;
    xDest = 0;
    v24 = (Ascent - hDest) / 2;
    if ( v22 <= 0 )
      v24 = v23;
    v25 = (CDisplay *)*((_QWORD *)this + 19);
    v36 = v28 + v24;
    CDisplay::PointFromPointuv(v25, &xDest, (const struct Ptls6::tagLSPOINTUV *)&v35, 0, 0);
    v26 = CDisplay::Zoom(*((CDisplay **)this + 19), v11);
    v27 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
    StretchBlt(v27, xDest.x, xDest.y, v26, hDest, hdcSrc, 0, 0, wSrc, wSrc, 0xCC0020u);
    SelectObject(hdcSrc, v19);
  }
  else
  {
    v9 = 0;
  }
  DeleteDC(hdcSrc);
  return v9;
}

```

## disassembly

```asm
0x180137be8  push    rbp
0x180137bea  push    rbx
0x180137beb  push    rsi
0x180137bec  push    rdi
0x180137bed  push    r12
0x180137bef  push    r13
0x180137bf1  push    r14
0x180137bf3  push    r15
0x180137bf5  lea     rbp, [rsp-1Fh]
0x180137bfa  sub     rsp, 0B8h
0x180137c01  mov     rax, [rcx+128h]
0x180137c08  mov     r14, rcx
0x180137c0b  test    rax, rax
0x180137c0e  jnz     short loc_180137C15
0x180137c10  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x180137c15  movzx   eax, byte ptr [rax+23h]
0x180137c19  mov     rcx, r14; this
0x180137c1c  imul    edx, eax, 168h; int
0x180137c22  call    ?LUtoDUZ@CMeasurerNoFC@@QEBAJJ@Z; CMeasurerNoFC::LUtoDUZ(long)
0x180137c27  cmp     cs:h, 0
0x180137c2f  mov     ecx, [r14+200h]
0x180137c36  mov     [rbp+57h+arg_18], eax
0x180137c39  mov     eax, [r14+64h]
0x180137c3d  mov     [rbp+57h+arg_10], eax
0x180137c40  mov     eax, [r14+204h]
0x180137c47  mov     [rbp+57h+var_90], eax
0x180137c4a  mov     dword ptr [rbp+57h+xDest], ecx
0x180137c4d  jnz     short loc_180137C58
0x180137c4f  call    ?InitializeOutlineBitmaps@@YAJXZ; InitializeOutlineBitmaps(void)
0x180137c54  test    eax, eax
0x180137c56  jnz     short loc_180137C7C
0x180137c58  mov     rcx, [r14+150h]
0x180137c5f  mov     rax, [rcx]
0x180137c62  mov     rax, [rax+30h]
0x180137c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137c6b  mov     rcx, rax; hdc
0x180137c6e  call    cs:__imp_CreateCompatibleDC
0x180137c74  mov     r12, rax
0x180137c77  test    rax, rax
0x180137c7a  jnz     short loc_180137C83
0x180137c7c  xor     eax, eax
0x180137c7e  jmp     loc_180137E6B
0x180137c83  mov     rax, [r14+128h]
0x180137c8a  test    rax, rax
0x180137c8d  jnz     short loc_180137C97
0x180137c8f  mov     rcx, r14; this
0x180137c92  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x180137c97  mov     r15d, 1
0x180137c9d  test    [rax+23h], r15b
0x180137ca1  jz      short loc_180137CB6
0x180137ca3  mov     rdi, cs:h
0x180137caa  lea     ebx, [r15+3]
0x180137cae  mov     [rbp+57h+arg_0], ebx
0x180137cb1  jmp     loc_180137D6A
0x180137cb6  mov     rdi, cs:qword_1802DF568
0x180137cbd  lea     rcx, [rbp+57h+var_88]; this
0x180137cc1  mov     ebx, 0Ah
0x180137cc6  mov     rdx, r14; struct CRchTxtPtr *
0x180137cc9  mov     [rbp+57h+arg_0], ebx
0x180137ccc  call    ??0CPFRunPtr@@QEAA@AEBVCRchTxtPtr@@@Z; CPFRunPtr::CPFRunPtr(CRchTxtPtr const &)
0x180137cd1  mov     r11d, [r14+60h]
0x180137cd5  lea     rcx, [rbp+57h+var_88]; this
0x180137cd9  call    ?GetCchLeft@CRunPtrBase@@QEBAJXZ; CRunPtrBase::GetCchLeft(void)
0x180137cde  cmp     r11d, eax
0x180137ce1  jge     short loc_180137D18
0x180137ce3  movups  xmm0, xmmword ptr [r14+10h]
0x180137ce8  lea     rcx, [rbp+57h+var_70]; this
0x180137cec  xor     r9d, r9d; int
0x180137cef  movsd   xmm1, qword ptr [r14+20h]
0x180137cf5  xor     r8d, r8d; int *
0x180137cf8  movups  [rbp+57h+var_70], xmm0
0x180137cfc  mov     edx, 3FFFFFFFh; int
0x180137d01  movups  xmm0, xmmword ptr [r14+28h]
0x180137d06  movsd   [rbp+57h+var_60], xmm1
0x180137d0b  movdqu  [rbp+57h+var_58], xmm0
0x180137d10  call    ?FindEOP@CTxtPtrEx@@QEAAJJPEAJH@Z; CTxtPtrEx::FindEOP(long,long *,int)
0x180137d15  mov     r11d, eax
0x180137d18  mov     edx, r11d; int
0x180137d1b  lea     rcx, [rbp+57h+var_88]; this
0x180137d1f  call    ?Move@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::Move(long)
0x180137d24  lea     rcx, [rbp+57h+var_88]; this
0x180137d28  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x180137d2d  test    eax, eax
0x180137d2f  jz      short loc_180137D3A
0x180137d31  mov     rdi, cs:qword_1802DF570
0x180137d38  jmp     short loc_180137D6A
0x180137d3a  mov     rax, [r14+128h]
0x180137d41  test    rax, rax
0x180137d44  jnz     short loc_180137D4E
0x180137d46  mov     rcx, r14; this
0x180137d49  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x180137d4e  movzx   ebx, byte ptr [rax+23h]
0x180137d52  lea     rcx, [rbp+57h+var_88]; this
0x180137d56  call    ?GetOutlineLevel@CPFRunPtr@@QEAAJXZ; CPFRunPtr::GetOutlineLevel(void)
0x180137d5b  cmp     ebx, eax
0x180137d5d  mov     ebx, 0Ah
0x180137d62  cmovl   rdi, cs:qword_1802DF578
0x180137d6a  test    rdi, rdi
0x180137d6d  jnz     short loc_180137D77
0x180137d6f  xor     r15d, r15d
0x180137d72  jmp     loc_180137E5F
0x180137d77  mov     rdx, rdi; h
0x180137d7a  mov     rcx, r12; hdc
0x180137d7d  call    cs:__imp_SelectObject
0x180137d83  mov     rcx, [r14+98h]; this
0x180137d8a  mov     edx, ebx; int
0x180137d8c  mov     rsi, rax
0x180137d8f  call    ?Zoom@CDisplay@@QEBAJJ@Z; CDisplay::Zoom(long)
0x180137d94  xor     r8d, r8d; struct CDisplay *
0x180137d97  lea     rcx, [r14+60h]; this
0x180137d9b  xor     edx, edx; bool
0x180137d9d  mov     edi, eax
0x180137d9f  call    ?GetAscent@CLine@@QEBAJ_NPEBVCDisplay@@@Z; CLine::GetAscent(bool,CDisplay const *)
0x180137da4  mov     r8d, eax
0x180137da7  mov     r9d, 2
0x180137dad  mov     eax, dword ptr [rbp+57h+xDest]
0x180137db0  sub     r8d, edi
0x180137db3  sub     eax, [rbp+57h+arg_10]
0x180137db6  mov     ecx, r8d
0x180137db9  add     eax, [rbp+57h+arg_18]
0x180137dbc  neg     ecx
0x180137dbe  mov     [rbp+57h+arg_10], eax
0x180137dc1  xor     r13d, r13d
0x180137dc4  mov     eax, r8d
0x180137dc7  mov     [rbp+57h+xDest], r13
0x180137dcb  cdq
0x180137dcc  mov     byte ptr [rsp+0F0h+hDest], r13b; bool
0x180137dd1  idiv    r9d
0x180137dd4  test    r8d, r8d
0x180137dd7  lea     rdx, [rbp+57h+xDest]; struct tagPOINT *
0x180137ddb  lea     r8, [rbp+57h+arg_10]; struct Ptls6::tagLSPOINTUV *
0x180137ddf  cmovle  eax, ecx
0x180137de2  mov     rcx, [r14+98h]; this
0x180137de9  add     eax, [rbp+57h+var_90]
0x180137dec  xor     r9d, r9d; bool
0x180137def  mov     [rbp+57h+arg_14], eax
0x180137df2  call    ?PointFromPointuv@CDisplay@@QEBAXAEAUtagPOINT@@AEBUtagLSPOINTUV@Ptls6@@_N2@Z; CDisplay::PointFromPointuv(tagPOINT &,Ptls6::tagLSPOINTUV const &,bool,bool)
0x180137df7  mov     rcx, [r14+98h]; this
0x180137dfe  mov     edx, ebx; int
0x180137e00  call    ?Zoom@CDisplay@@QEBAJJ@Z; CDisplay::Zoom(long)
0x180137e05  mov     rcx, [r14+150h]
0x180137e0c  mov     ebx, eax
0x180137e0e  mov     rdx, [rcx]
0x180137e11  mov     rax, [rdx+30h]
0x180137e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137e1a  mov     ecx, [rbp+57h+arg_0]
0x180137e1d  mov     r9d, ebx; wDest
0x180137e20  mov     r8d, dword ptr [rbp+57h+xDest+4]; yDest
0x180137e24  mov     edx, dword ptr [rbp+57h+xDest]; xDest
0x180137e27  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x180137e2f  mov     [rsp+0F0h+hSrc], ecx; hSrc
0x180137e33  mov     [rsp+0F0h+wSrc], ecx; wSrc
0x180137e37  mov     rcx, rax; hdcDest
0x180137e3a  mov     [rsp+0F0h+ySrc], r13d; ySrc
0x180137e3f  mov     [rsp+0F0h+xSrc], r13d; xSrc
0x180137e44  mov     [rsp+0F0h+hdcSrc], r12; hdcSrc
0x180137e49  mov     [rsp+0F0h+hDest], edi; hDest
0x180137e4d  call    cs:__imp_StretchBlt
0x180137e53  mov     rdx, rsi; h
0x180137e56  mov     rcx, r12; hdc
0x180137e59  call    cs:__imp_SelectObject
0x180137e5f  mov     rcx, r12; hdc
0x180137e62  call    cs:__imp_DeleteDC
0x180137e68  mov     eax, r15d
0x180137e6b  add     rsp, 0B8h
0x180137e72  pop     r15
0x180137e74  pop     r14
0x180137e76  pop     r13
0x180137e78  pop     r12
0x180137e7a  pop     rdi
0x180137e7b  pop     rsi
0x180137e7c  pop     rbx
0x180137e7d  pop     rbp
0x180137e7e  retn
```
