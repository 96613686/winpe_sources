# xpsrdr::CreateSolidColorBrush(xpsrdr::RenderState &,_D3DCOLORVALUE const &,float *)

- ea: `0x1800415dc`
- end: `0x1800416a2`
- name: `?CreateSolidColorBrush@xpsrdr@@YA?AV?$shared_ptr@UID2D1Brush@@@std@@AEAURenderState@1@AEBU_D3DCOLORVALUE@@PEAM@Z`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180041548`
- `0x1800416a8`

## callees

- `0x18000d7f8`
- `0x18000e130`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x180037278`
- `0x1800415dc`
- `0x18004185c`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xpsrdr::CreateSolidColorBrush(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v5; // rdx
  __int64 RenderTargetStackTop; // rax
  __int64 v7; // r10
  __int64 (__fastcall *v8)(__int64, __int64, _QWORD, _QWORD *); // rax
  __int64 v9; // r11
  int v10; // edi
  int v11; // edx
  const char *v12; // r8
  int v13; // r9d
  _BYTE v15[16]; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v16[3]; // [rsp+48h] [rbp-18h] BYREF
  xpsrdr *v17; // [rsp+88h] [rbp+28h] BYREF

  if ( a4 )
    *a4 = *(_DWORD *)(a3 + 12);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v15);
  LODWORD(v17) = 0;
  RenderTargetStackTop = xpsrdr::RenderState::GetRenderTargetStackTop(v5);
  v7 = std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(RenderTargetStackTop);
  v8 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD *))(*(_QWORD *)v7 + 64LL);
  v16[0] = 0;
  v16[1] = &v17;
  v16[2] = v15;
  v10 = v8(v7, v9, 0, v16);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v16);
  if ( (int)v17 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v17, v11, v12, v13);
  if ( v10 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, v11, v12, v13);
  std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(a1, v15);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v15);
  return a1;
}

```

## disassembly

```asm
0x1800415dc  mov     [rsp-8+arg_0], rbx
0x1800415e1  mov     [rsp-8+arg_8], rdi
0x1800415e6  push    rbp
0x1800415e7  mov     rbp, rsp
0x1800415ea  sub     rsp, 60h
0x1800415ee  mov     r11, r8
0x1800415f1  mov     rbx, rcx
0x1800415f4  test    r9, r9
0x1800415f7  jz      short loc_180041600
0x1800415f9  mov     eax, [r8+0Ch]
0x1800415fd  mov     [r9], eax
0x180041600  lea     rcx, [rbp+var_28]
0x180041604  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180041609  nop
0x18004160a  mov     dword ptr [rbp+arg_18], 0
0x180041611  mov     rcx, rdx
0x180041614  call    ?GetRenderTargetStackTop@RenderState@xpsrdr@@QEBAAEBV?$shared_ptr@UID2D1RenderTarget@@@std@@XZ; xpsrdr::RenderState::GetRenderTargetStackTop(void)
0x180041619  mov     rcx, rax
0x18004161c  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x180041621  mov     r10, rax
0x180041624  mov     rcx, [rax]
0x180041627  mov     rax, [rcx+40h]
0x18004162b  mov     [rbp+var_18], 0
0x180041633  lea     rcx, [rbp+arg_18]
0x180041637  mov     [rbp+var_10], rcx
0x18004163b  lea     rcx, [rbp+var_28]
0x18004163f  mov     [rbp+var_8], rcx
0x180041643  lea     r9, [rbp+var_18]
0x180041647  xor     r8d, r8d
0x18004164a  mov     rdx, r11
0x18004164d  mov     rcx, r10
0x180041650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041655  mov     edi, eax
0x180041657  lea     rcx, [rbp+var_18]
0x18004165b  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180041660  mov     ecx, dword ptr [rbp+arg_18]; this
0x180041663  test    ecx, ecx
0x180041665  jns     short loc_18004166D
0x180041667  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004166d  test    edi, edi
0x18004166f  jns     short loc_180041679
0x180041671  mov     ecx, edi; this
0x180041673  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180041679  lea     rdx, [rbp+var_28]
0x18004167d  mov     rcx, rbx
0x180041680  call    ??$?0UIWICColorTransform@@$0A@@?$shared_ptr@UIWICBitmapSource@@@std@@QEAA@$$QEAV?$shared_ptr@UIWICColorTransform@@@1@@Z; std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(std::shared_ptr<IWICColorTransform> &&)
0x180041685  nop
0x180041686  lea     rcx, [rbp+var_28]
0x18004168a  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18004168f  mov     rax, rbx
0x180041692  mov     rbx, [rsp+60h+arg_0]
0x180041697  mov     rdi, [rsp+60h+arg_8]
0x18004169c  add     rsp, 60h
0x1800416a0  pop     rbp
0x1800416a1  retn
```
