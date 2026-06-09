# xgc::CDeviceContext::CDeviceContext(xpsrdr::RenderState &,IWICBitmap *)

- ea: `0x180024584`
- end: `0x18002469f`
- name: `??0CDeviceContext@xgc@@QEAA@AEAURenderState@xpsrdr@@PEAUIWICBitmap@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(xgc::CDeviceContext *__hidden this, struct xpsrdr::RenderState *, struct IWICBitmap *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800175dc`

## callees

- `0x18000e15c`
- `0x180013854`
- `0x18002421c`
- `0x180024280`
- `0x1800242e4`
- `0x180024584`
- `0x180027054`
- `0x1800272a0`
- `0x180027a3c`
- `0x180037278`
- `0x1800372e4`
- `0x18004a010`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18002459e`
- `GDI32!CreateCompatibleDC` at `0x18002459e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
xgc::CDeviceContext *__fastcall xgc::CDeviceContext::CDeviceContext(
        xgc::CDeviceContext *this,
        struct xpsrdr::RenderState *a2,
        struct IWICBitmap *a3)
{
  int v5; // eax
  const char *v6; // rdx
  const char *v7; // r8
  int v8; // r9d
  int v9; // eax
  xpsrdr *v10; // rcx
  int v11; // eax
  int v12; // edx
  const char *v13; // r8
  int v14; // r9d
  double v16[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v17; // [rsp+58h] [rbp+28h] BYREF
  unsigned int v18; // [rsp+60h] [rbp+30h] BYREF
  double v19; // [rsp+68h] [rbp+38h] BYREF

  *(_QWORD *)this = a2;
  *((_QWORD *)this + 4) = CreateCompatibleDC(0);
  std::deque<D2D_MATRIX_3X2_F>::deque<D2D_MATRIX_3X2_F>((char *)this + 64);
  *((_QWORD *)this + 13) = a3;
  *((_QWORD *)this + 14) = 0;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>((char *)this + 120);
  *((_QWORD *)this + 17) = 0;
  xgc::GDIResources<HBRUSH__ *,unsigned long>::GDIResources<HBRUSH__ *,unsigned long>((char *)this + 144);
  xgc::GDIResources<HPEN__ *,KeyPen>::GDIResources<HPEN__ *,KeyPen>((char *)this + 200);
  xgc::GDIResources<HFONT__ *,tagLOGFONTW>::GDIResources<HFONT__ *,tagLOGFONTW>((char *)this + 256);
  *((_QWORD *)this + 39) = 0;
  xgc::CDeviceContext::init(this);
  v19 = 0.0;
  v16[0] = 0.0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, double *, double *))(**((_QWORD **)this + 13) + 40LL))(
         *((_QWORD *)this + 13),
         &v19,
         v16);
  if ( v5 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v5, (int)v6, v7, v8);
  v9 = (int)v19;
  *((_DWORD *)this + 2) = (int)v19;
  v10 = (xpsrdr *)(unsigned int)(int)v16[0];
  *((_DWORD *)this + 3) = (_DWORD)v10;
  if ( !v9 || !(_DWORD)v10 )
    xpsrdr::ThrowLogicException(v10, v6, (int)v7);
  v18 = 0;
  v17 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, unsigned int *))(**((_QWORD **)this + 13) + 24LL))(
          *((_QWORD *)this + 13),
          &v18,
          &v17);
  if ( v11 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v11, v12, v13, v14);
  xgc::CDeviceContext::SelectBitmap(this, v18, v17);
  xgc::CDeviceContext::SetupDeviceTransform(this);
  return this;
}

```

## disassembly

```asm
0x180024584  mov     [rsp-18h+arg_0], rcx
0x180024589  push    rbp
0x18002458a  push    rbx
0x18002458b  push    rdi
0x18002458c  mov     rbp, rsp
0x18002458f  sub     rsp, 30h
0x180024593  mov     rbx, r8
0x180024596  mov     rdi, rcx
0x180024599  mov     [rcx], rdx
0x18002459c  xor     ecx, ecx; hdc
0x18002459e  call    cs:__imp_CreateCompatibleDC
0x1800245a4  mov     [rdi+20h], rax
0x1800245a8  lea     rcx, [rdi+40h]
0x1800245ac  call    ??0?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@QEAA@XZ; std::deque<D2D_MATRIX_3X2_F>::deque<D2D_MATRIX_3X2_F>(void)
0x1800245b1  nop
0x1800245b2  mov     [rdi+68h], rbx
0x1800245b6  xor     ebx, ebx
0x1800245b8  mov     [rdi+70h], rbx
0x1800245bc  lea     rcx, [rdi+78h]
0x1800245c0  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800245c5  nop
0x1800245c6  mov     [rdi+88h], rbx
0x1800245cd  lea     rcx, [rdi+90h]
0x1800245d4  call    ??0?$GDIResources@PEAUHBRUSH__@@K@xgc@@QEAA@XZ; xgc::GDIResources<HBRUSH__ *,ulong>::GDIResources<HBRUSH__ *,ulong>(void)
0x1800245d9  nop
0x1800245da  lea     rcx, [rdi+0C8h]
0x1800245e1  call    ??0?$GDIResources@PEAUHPEN__@@UKeyPen@@@xgc@@QEAA@XZ; xgc::GDIResources<HPEN__ *,KeyPen>::GDIResources<HPEN__ *,KeyPen>(void)
0x1800245e6  nop
0x1800245e7  lea     rcx, [rdi+100h]
0x1800245ee  call    ??0?$GDIResources@PEAUHFONT__@@UtagLOGFONTW@@@xgc@@QEAA@XZ; xgc::GDIResources<HFONT__ *,tagLOGFONTW>::GDIResources<HFONT__ *,tagLOGFONTW>(void)
0x1800245f3  nop
0x1800245f4  mov     [rdi+138h], rbx
0x1800245fb  mov     rcx, rdi; this
0x1800245fe  call    ?init@CDeviceContext@xgc@@AEAAXXZ; xgc::CDeviceContext::init(void)
0x180024603  xorps   xmm0, xmm0
0x180024606  movsd   [rbp+arg_18], xmm0
0x18002460b  movsd   [rbp+var_10], xmm0
0x180024610  mov     rcx, [rdi+68h]
0x180024614  mov     rax, [rcx]
0x180024617  lea     r8, [rbp+var_10]
0x18002461b  lea     rdx, [rbp+arg_18]
0x18002461f  mov     rax, [rax+28h]
0x180024623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024628  test    eax, eax
0x18002462a  jns     short loc_180024634
0x18002462c  mov     ecx, eax; this
0x18002462e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180024634  cvttsd2si eax, [rbp+arg_18]
0x180024639  mov     [rdi+8], eax
0x18002463c  cvttsd2si ecx, [rbp+var_10]; this
0x180024641  mov     [rdi+0Ch], ecx
0x180024644  test    eax, eax
0x180024646  jz      short loc_180024699
0x180024648  test    ecx, ecx
0x18002464a  jz      short loc_180024699
0x18002464c  mov     [rbp+arg_10], ebx
0x18002464f  mov     [rbp+arg_8], ebx
0x180024652  mov     rcx, [rdi+68h]
0x180024656  mov     rax, [rcx]
0x180024659  lea     r8, [rbp+arg_8]
0x18002465d  lea     rdx, [rbp+arg_10]
0x180024661  mov     rax, [rax+18h]
0x180024665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002466a  test    eax, eax
0x18002466c  jns     short loc_180024676
0x18002466e  mov     ecx, eax; this
0x180024670  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180024676  mov     r8d, [rbp+arg_8]; unsigned int
0x18002467a  mov     edx, [rbp+arg_10]; unsigned int
0x18002467d  mov     rcx, rdi; this
0x180024680  call    ?SelectBitmap@CDeviceContext@xgc@@AEAAXII@Z; xgc::CDeviceContext::SelectBitmap(uint,uint)
0x180024685  mov     rcx, rdi; this
0x180024688  call    ?SetupDeviceTransform@CDeviceContext@xgc@@AEAAXXZ; xgc::CDeviceContext::SetupDeviceTransform(void)
0x18002468d  nop
0x18002468e  mov     rax, rdi
0x180024691  add     rsp, 30h
0x180024695  pop     rdi
0x180024696  pop     rbx
0x180024697  pop     rbp
0x180024698  retn
0x180024699  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
```
