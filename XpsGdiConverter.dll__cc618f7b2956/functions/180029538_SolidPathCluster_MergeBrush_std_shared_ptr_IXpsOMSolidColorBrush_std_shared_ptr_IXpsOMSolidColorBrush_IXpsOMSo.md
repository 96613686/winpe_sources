# SolidPathCluster::MergeBrush(std::shared_ptr<IXpsOMSolidColorBrush>,std::shared_ptr<IXpsOMSolidColorBrush>,IXpsOMSolidColorBrush * *)

- ea: `0x180029538`
- end: `0x180029695`
- name: `?MergeBrush@SolidPathCluster@@AEAAJV?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@0PEAPEAUIXpsOMSolidColorBrush@@@Z`
- size: `349`
- prototype: `__int64 __fastcall(SolidPathCluster *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002990c`

## callees

- `0x180008830`
- `0x18000da08`
- `0x18000e0d8`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x18002914c`
- `0x180029538`
- `0x18002969c`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SolidPathCluster::MergeBrush(SolidPathCluster *this, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v8; // r9
  int v9; // ebx
  struct IXpsOMObjectFactory *XpsFactory; // rcx
  struct IXpsOMObjectFactoryVtbl *lpVtbl; // rax
  int v12; // ebx
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  __int64 v16; // rcx
  xpsrdr *v18; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v19[3]; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v21[4]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v22[48]; // [rsp+80h] [rbp-9h] BYREF

  v21[2] = a2;
  v21[3] = a3;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v20);
  if ( v8 )
  {
    std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v21);
    std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v21, a3);
    std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v19);
    std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v19, a2);
    SolidPathCluster::MergeColor(this, v22, v19, v21);
    LODWORD(v18) = 0;
    XpsFactory = SolidPathCluster::GetXpsFactory(this);
    lpVtbl = XpsFactory->lpVtbl;
    v19[0] = 0;
    v19[1] = &v18;
    v19[2] = v20;
    v12 = ((__int64 (__fastcall *)(struct IXpsOMObjectFactory *, _BYTE *, _QWORD, _QWORD *))lpVtbl->CreateSolidColorBrush)(
            XpsFactory,
            v22,
            0,
            v19);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v19);
    if ( (int)v18 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v13, v14, v15);
    if ( v12 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, v13, v14, v15);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v20[0] + 48LL))(v20[0]);
    if ( v9 >= 0 )
    {
      v16 = v20[0];
      *a4 = v20[0];
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  else
  {
    v9 = -2147024809;
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v20);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(a2);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(a3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180029538  push    rbp
0x18002953a  push    rbx
0x18002953b  push    rsi
0x18002953c  push    rdi
0x18002953d  push    r14
0x18002953f  lea     rbp, [rsp-37h]
0x180029544  sub     rsp, 0C0h
0x18002954b  mov     rax, cs:__security_cookie
0x180029552  xor     rax, rsp
0x180029555  mov     [rbp+57h+var_30], rax
0x180029559  mov     r14, r9
0x18002955c  mov     rsi, r8
0x18002955f  mov     rdi, rdx
0x180029562  mov     rbx, rcx
0x180029565  mov     [rbp+57h+var_70], rdx
0x180029569  mov     [rbp+57h+var_68], r8
0x18002956d  lea     rcx, [rbp+57h+var_90]
0x180029571  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180029576  nop
0x180029577  test    r9, r9
0x18002957a  jnz     short loc_180029586
0x18002957c  mov     ebx, 80070057h
0x180029581  jmp     loc_18002965E
0x180029586  lea     rcx, [rbp+57h+var_80]
0x18002958a  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18002958f  mov     rdx, rsi
0x180029592  lea     rcx, [rbp+57h+var_80]
0x180029596  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x18002959b  lea     rcx, [rbp+57h+var_A8]
0x18002959f  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x1800295a4  mov     rdx, rdi
0x1800295a7  lea     rcx, [rbp+57h+var_A8]
0x1800295ab  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x1800295b0  lea     r9, [rbp+57h+var_80]
0x1800295b4  lea     r8, [rbp+57h+var_A8]
0x1800295b8  lea     rdx, [rbp+57h+var_60]
0x1800295bc  mov     rcx, rbx
0x1800295bf  call    ?MergeColor@SolidPathCluster@@AEAA?AU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024@@V?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@0@Z; SolidPathCluster::MergeColor(std::shared_ptr<IXpsOMSolidColorBrush>,std::shared_ptr<IXpsOMSolidColorBrush>)
0x1800295c4  mov     dword ptr [rbp+57h+var_B0], 0
0x1800295cb  mov     rcx, rbx; this
0x1800295ce  call    ?GetXpsFactory@SolidPathCluster@@AEAAPEAUIXpsOMObjectFactory@@XZ; SolidPathCluster::GetXpsFactory(void)
0x1800295d3  mov     rcx, rax
0x1800295d6  mov     rax, [rax]
0x1800295d9  mov     [rbp+57h+var_A8], 0
0x1800295e1  lea     rdx, [rbp+57h+var_B0]
0x1800295e5  mov     [rbp+57h+var_A0], rdx
0x1800295e9  lea     rdx, [rbp+57h+var_90]
0x1800295ed  mov     [rbp+57h+var_98], rdx
0x1800295f1  lea     r9, [rbp+57h+var_A8]
0x1800295f5  xor     r8d, r8d
0x1800295f8  lea     rdx, [rbp+57h+var_60]
0x1800295fc  mov     rax, [rax+0B8h]
0x180029603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029608  mov     ebx, eax
0x18002960a  lea     rcx, [rbp+57h+var_A8]
0x18002960e  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180029613  mov     ecx, dword ptr [rbp+57h+var_B0]; this
0x180029616  test    ecx, ecx
0x180029618  jns     short loc_180029620
0x18002961a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180029620  test    ebx, ebx
0x180029622  jns     short loc_18002962C
0x180029624  mov     ecx, ebx; this
0x180029626  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002962c  mov     rcx, [rbp+57h+var_90]
0x180029630  mov     rax, [rcx]
0x180029633  movss   xmm1, cs:__real@3f800000
0x18002963b  mov     rax, [rax+30h]
0x18002963f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029644  mov     ebx, eax
0x180029646  test    eax, eax
0x180029648  js      short loc_18002965E
0x18002964a  mov     rcx, [rbp+57h+var_90]
0x18002964e  mov     [r14], rcx
0x180029651  mov     rdx, [rcx]
0x180029654  mov     rax, [rdx+8]
0x180029658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002965d  nop
0x18002965e  lea     rcx, [rbp+57h+var_90]
0x180029662  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029667  nop
0x180029668  mov     rcx, rdi
0x18002966b  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029670  nop
0x180029671  mov     rcx, rsi
0x180029674  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029679  mov     eax, ebx
0x18002967b  mov     rcx, [rbp+57h+var_30]
0x18002967f  xor     rcx, rsp; StackCookie
0x180029682  call    __security_check_cookie
0x180029687  add     rsp, 0C0h
0x18002968e  pop     r14
0x180029690  pop     rdi
0x180029691  pop     rsi
0x180029692  pop     rbx
0x180029693  pop     rbp
0x180029694  retn
```
