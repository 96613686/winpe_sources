# xpsrdr::TileBrushBuilder::CreateRenderTarget(std::shared_ptr<ID2D1DeviceContext> &,std::shared_ptr<ID2D1CommandList> &)

- ea: `0x180046020`
- end: `0x1800461bf`
- name: `?CreateRenderTarget@TileBrushBuilder@xpsrdr@@AEAAXAEAV?$shared_ptr@UID2D1DeviceContext@@@std@@AEAV?$shared_ptr@UID2D1CommandList@@@4@@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180045b18`

## callees

- `0x18000d7f8`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x180037278`
- `0x18004185c`
- `0x180046020`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
double __fastcall xpsrdr::TileBrushBuilder::CreateRenderTarget(__int64 a1, __int64 **a2, __int64 **a3)
{
  __int64 v5; // r9
  __int64 RenderTargetStackTop; // rax
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rax
  int v8; // ebx
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // ebx
  int v15; // edx
  const char *v16; // r8
  int v17; // r9d
  __int64 *v18; // rcx
  __int64 v19; // rax
  int v20; // ebx
  int v21; // edx
  const char *v22; // r8
  int v23; // r9d
  _QWORD v25[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v26[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v27; // [rsp+40h] [rbp-28h] BYREF
  xpsrdr **v28; // [rsp+48h] [rbp-20h]
  __int64 **v29; // [rsp+50h] [rbp-18h]
  xpsrdr *v30; // [rsp+90h] [rbp+28h] BYREF

  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v26);
  LODWORD(v30) = 0;
  RenderTargetStackTop = xpsrdr::RenderState::GetRenderTargetStackTop(*(_QWORD *)(v5 + 32));
  v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(RenderTargetStackTop);
  v27 = 0;
  v28 = &v30;
  v29 = (__int64 **)v26;
  v8 = (**v7)(v7, &GUID_e8f7fe7a_191c_466d_ad95_975678bda998, &v27);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v27);
  if ( (int)v30 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v30, v9, v10, v11);
  if ( v8 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v8, v9, v10, v11);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v25);
  LODWORD(v30) = 0;
  v12 = *(_QWORD *)v26[0];
  v27 = 0;
  v28 = &v30;
  v29 = (__int64 **)v25;
  (*(void (__fastcall **)(_QWORD, __int64 *))(v12 + 584))(v26[0], &v27);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v27);
  LODWORD(v30) = 0;
  v13 = *(_QWORD *)v25[0];
  v27 = 0;
  v28 = &v30;
  v29 = a2;
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(v13 + 32))(v25[0], 0, &v27);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v27);
  if ( (int)v30 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v30, v15, v16, v17);
  if ( v14 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v14, v15, v16, v17);
  LODWORD(v30) = 0;
  v18 = *a2;
  v19 = **a2;
  v27 = 0;
  v28 = &v30;
  v29 = a3;
  v20 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v19 + 536))(v18, &v27);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v27);
  if ( (int)v30 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v30, v21, v22, v23);
  if ( v20 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v20, v21, v22, v23);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v25);
  return std::_Ptr_base<ID2D1RenderTarget>::_Decref(v26);
}

```

## disassembly

```asm
0x180046020  push    rbp
0x180046022  push    rbx
0x180046023  push    rsi
0x180046024  push    rdi
0x180046025  mov     rbp, rsp
0x180046028  sub     rsp, 68h
0x18004602c  mov     rsi, r8
0x18004602f  mov     rdi, rdx
0x180046032  mov     r9, rcx
0x180046035  lea     rcx, [rbp+var_38]
0x180046039  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18004603e  nop
0x18004603f  mov     dword ptr [rbp+arg_0], 0
0x180046046  mov     rcx, [r9+20h]
0x18004604a  call    ?GetRenderTargetStackTop@RenderState@xpsrdr@@QEBAAEBV?$shared_ptr@UID2D1RenderTarget@@@std@@XZ; xpsrdr::RenderState::GetRenderTargetStackTop(void)
0x18004604f  mov     rcx, rax
0x180046052  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x180046057  mov     r9, rax
0x18004605a  mov     [rbp+var_28], 0
0x180046062  lea     rax, [rbp+arg_0]
0x180046066  mov     [rbp+var_20], rax
0x18004606a  lea     rax, [rbp+var_38]
0x18004606e  mov     [rbp+var_18], rax
0x180046072  mov     rcx, [r9]
0x180046075  mov     rax, [rcx]
0x180046078  lea     r8, [rbp+var_28]
0x18004607c  lea     rdx, _GUID_e8f7fe7a_191c_466d_ad95_975678bda998
0x180046083  mov     rcx, r9
0x180046086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004608b  mov     ebx, eax
0x18004608d  lea     rcx, [rbp+var_28]
0x180046091  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180046096  mov     ecx, dword ptr [rbp+arg_0]; this
0x180046099  test    ecx, ecx
0x18004609b  jns     short loc_1800460A3
0x18004609d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800460a3  test    ebx, ebx
0x1800460a5  jns     short loc_1800460AF
0x1800460a7  mov     ecx, ebx; this
0x1800460a9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800460af  lea     rcx, [rbp+var_48]
0x1800460b3  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800460b8  nop
0x1800460b9  mov     dword ptr [rbp+arg_0], 0
0x1800460c0  mov     rcx, [rbp+var_38]
0x1800460c4  mov     rax, [rcx]
0x1800460c7  mov     [rbp+var_28], 0
0x1800460cf  lea     rdx, [rbp+arg_0]
0x1800460d3  mov     [rbp+var_20], rdx
0x1800460d7  lea     rdx, [rbp+var_48]
0x1800460db  mov     [rbp+var_18], rdx
0x1800460df  lea     rdx, [rbp+var_28]
0x1800460e3  mov     rax, [rax+248h]
0x1800460ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460ef  nop
0x1800460f0  lea     rcx, [rbp+var_28]
0x1800460f4  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800460f9  mov     dword ptr [rbp+arg_0], 0
0x180046100  mov     rcx, [rbp+var_48]
0x180046104  mov     rax, [rcx]
0x180046107  mov     [rbp+var_28], 0
0x18004610f  lea     rdx, [rbp+arg_0]
0x180046113  mov     [rbp+var_20], rdx
0x180046117  mov     [rbp+var_18], rdi
0x18004611b  lea     r8, [rbp+var_28]
0x18004611f  xor     edx, edx
0x180046121  mov     rax, [rax+20h]
0x180046125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004612a  mov     ebx, eax
0x18004612c  lea     rcx, [rbp+var_28]
0x180046130  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180046135  mov     ecx, dword ptr [rbp+arg_0]; this
0x180046138  test    ecx, ecx
0x18004613a  jns     short loc_180046142
0x18004613c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180046142  test    ebx, ebx
0x180046144  jns     short loc_18004614E
0x180046146  mov     ecx, ebx; this
0x180046148  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004614e  mov     dword ptr [rbp+arg_0], 0
0x180046155  mov     rcx, [rdi]
0x180046158  mov     rax, [rcx]
0x18004615b  mov     [rbp+var_28], 0
0x180046163  lea     rdx, [rbp+arg_0]
0x180046167  mov     [rbp+var_20], rdx
0x18004616b  mov     [rbp+var_18], rsi
0x18004616f  lea     rdx, [rbp+var_28]
0x180046173  mov     rax, [rax+218h]
0x18004617a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004617f  mov     ebx, eax
0x180046181  lea     rcx, [rbp+var_28]
0x180046185  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18004618a  mov     ecx, dword ptr [rbp+arg_0]; this
0x18004618d  test    ecx, ecx
0x18004618f  jns     short loc_180046197
0x180046191  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180046197  test    ebx, ebx
0x180046199  jns     short loc_1800461A3
0x18004619b  mov     ecx, ebx; this
0x18004619d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800461a3  lea     rcx, [rbp+var_48]
0x1800461a7  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800461ac  nop
0x1800461ad  lea     rcx, [rbp+var_38]
0x1800461b1  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800461b6  add     rsp, 68h
0x1800461ba  pop     rdi
0x1800461bb  pop     rsi
0x1800461bc  pop     rbx
0x1800461bd  pop     rbp
0x1800461be  retn
```
