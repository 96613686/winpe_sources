# xpsrdr::TileBrushBuilder::CreateBitmapFromWicBitmap(std::shared_ptr<xpsrdr::Image> const &,std::shared_ptr<ID2D1DeviceContext> &)

- ea: `0x180044f78`
- end: `0x18004515b`
- name: `?CreateBitmapFromWicBitmap@TileBrushBuilder@xpsrdr@@AEAA?AV?$shared_ptr@UID2D1Bitmap@@@std@@AEBV?$shared_ptr@UImage@xpsrdr@@@4@AEAV?$shared_ptr@UID2D1DeviceContext@@@4@@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180045164`

## callees

- `0x180008830`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x1800184e8`
- `0x18001df50`
- `0x1800229e8`
- `0x180037278`
- `0x180044b04`
- `0x180044b78`
- `0x180044f78`
- `0x18004686c`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xpsrdr::TileBrushBuilder::CreateBitmapFromWicBitmap(__int64 a1, __int64 a2, _QWORD *a3, __int64 *a4)
{
  _QWORD *v8; // r8
  __int64 v9; // r8
  xpsrdr **v10; // rax
  __int64 v11; // rbx
  float v12; // xmm0_4
  float v13; // xmm0_4
  __int64 v14; // rcx
  __int64 v15; // rdx
  int v16; // ebx
  int v17; // edx
  const char *v18; // r8
  int v19; // r9d
  __int64 v20; // rax
  int v21; // xmm7_4
  int v22; // xmm6_4
  __int64 v23; // rbx
  xpsrdr *v25; // [rsp+38h] [rbp-49h] BYREF
  int v26; // [rsp+40h] [rbp-41h]
  _QWORD v27[4]; // [rsp+48h] [rbp-39h] BYREF
  _QWORD v28[2]; // [rsp+68h] [rbp-19h] BYREF
  int v29; // [rsp+78h] [rbp-9h]
  int v30; // [rsp+7Ch] [rbp-5h]

  v27[3] = a2;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(a2);
  v26 = 1;
  xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::find(
    *(_QWORD *)(a1 + 32) + 320LL,
    &v25,
    *v8);
  v10 = (xpsrdr **)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                     *(_QWORD *)(a1 + 32) + 320LL,
                     (__int64)v28,
                     v9);
  if ( v25 == *v10 )
  {
    LODWORD(v25) = 0;
    v14 = *a4;
    v27[0] = 0;
    v27[1] = &v25;
    v27[2] = a2;
    v15 = *a3;
    v28[0] = 0;
    v28[1] = *(_QWORD *)(v15 + 60);
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, _QWORD *))(*(_QWORD *)v14 + 40LL))(
            v14,
            *(_QWORD *)(v15 + 32),
            v28,
            v27);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v27);
    if ( (int)v25 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v25, v17, v18, v19);
    if ( v16 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v16, v17, v18, v19);
    xpsrdr::D2DImageData::D2DImageData((xpsrdr::D2DImageData *)v28);
    std::shared_ptr<ID2D1Brush>::operator=(v28, a2);
    v20 = *(_QWORD *)(a1 + 48);
    v29 = *(_DWORD *)(v20 + 12);
    v21 = v29;
    v30 = *(_DWORD *)(v20 + 8);
    v22 = v30;
    v23 = xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::operator[](
            *(_QWORD *)(a1 + 32) + 320LL,
            *a3);
    std::shared_ptr<ID2D1Brush>::operator=(v23, v28);
    *(_DWORD *)(v23 + 16) = v21;
    *(_DWORD *)(v23 + 20) = v22;
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v28);
  }
  else
  {
    v11 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(&v25);
    std::shared_ptr<ID2D1Brush>::operator=(a2, v11 + 32);
    v12 = *(float *)(*(_QWORD *)(a1 + 48) + 12LL);
    if ( v12 > *(float *)(v11 + 48) )
      *(float *)(v11 + 48) = v12;
    v13 = *(float *)(*(_QWORD *)(a1 + 48) + 8LL);
    if ( v13 > *(float *)(v11 + 52) )
      *(float *)(v11 + 52) = v13;
  }
  return a2;
}

```

## disassembly

```asm
0x180044f78  mov     rax, rsp
0x180044f7b  push    rbp
0x180044f7c  push    rbx
0x180044f7d  push    rsi
0x180044f7e  push    rdi
0x180044f7f  push    r12
0x180044f81  push    r14
0x180044f83  lea     rbp, [rax-5Fh]
0x180044f87  sub     rsp, 0A8h
0x180044f8e  movaps  xmmword ptr [rax-48h], xmm6
0x180044f92  movaps  xmmword ptr [rax-58h], xmm7
0x180044f96  mov     rax, cs:__security_cookie
0x180044f9d  xor     rax, rsp
0x180044fa0  mov     [rbp+57h+var_58], rax
0x180044fa4  mov     rbx, r9
0x180044fa7  mov     r14, r8
0x180044faa  mov     rdi, rdx
0x180044fad  mov     rsi, rcx
0x180044fb0  mov     [rbp+57h+var_78], rdx
0x180044fb4  mov     [rbp+57h+var_98], 0
0x180044fbb  mov     rcx, rdx
0x180044fbe  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180044fc3  mov     [rbp+57h+var_98], 1
0x180044fca  mov     rcx, [rsi+20h]
0x180044fce  mov     r12d, 140h
0x180044fd4  add     rcx, r12
0x180044fd7  mov     r8, [r8]
0x180044fda  lea     rdx, [rbp+57h+var_A0]
0x180044fde  call    ?find@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::find(std::wstring const &)
0x180044fe3  mov     rcx, [rsi+20h]
0x180044fe7  add     rcx, r12
0x180044fea  lea     rdx, [rbp+57h+var_70]
0x180044fee  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x180044ff3  mov     rcx, [rax]
0x180044ff6  cmp     [rbp+57h+var_A0], rcx
0x180044ffa  jz      short loc_180045045
0x180044ffc  lea     rcx, [rbp+57h+var_A0]
0x180045000  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180045005  mov     rbx, rax
0x180045008  lea     rdx, [rax+20h]
0x18004500c  mov     rcx, rdi
0x18004500f  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x180045014  mov     rcx, [rsi+30h]
0x180045018  movss   xmm0, dword ptr [rcx+0Ch]
0x18004501d  comiss  xmm0, dword ptr [rbx+30h]
0x180045021  jbe     short loc_180045028
0x180045023  movss   dword ptr [rbx+30h], xmm0
0x180045028  mov     rcx, [rsi+30h]
0x18004502c  movss   xmm0, dword ptr [rcx+8]
0x180045031  comiss  xmm0, dword ptr [rbx+34h]
0x180045035  jbe     loc_18004512D
0x18004503b  movss   dword ptr [rbx+34h], xmm0
0x180045040  jmp     loc_18004512D
0x180045045  mov     dword ptr [rbp+57h+var_A0], 0
0x18004504c  mov     rcx, [rbx]
0x18004504f  mov     [rbp+57h+var_90], 0
0x180045057  lea     rax, [rbp+57h+var_A0]
0x18004505b  mov     [rbp+57h+var_88], rax
0x18004505f  mov     [rbp+57h+var_80], rdi
0x180045063  mov     rdx, [r14]
0x180045066  mov     qword ptr [rbp+57h+var_70], 0
0x18004506e  mov     rax, qword ptr [rbp+57h+var_70]
0x180045072  mov     qword ptr [rbp+57h+var_70], rax
0x180045076  movss   xmm0, dword ptr [rdx+3Ch]
0x18004507b  movss   dword ptr [rbp+57h+var_70+8], xmm0
0x180045080  movss   xmm1, dword ptr [rdx+40h]
0x180045085  movss   dword ptr [rbp+57h+var_70+0Ch], xmm1
0x18004508a  movups  xmm0, [rbp+57h+var_70]
0x18004508e  movups  [rbp+57h+var_70], xmm0
0x180045092  mov     rax, [rcx]
0x180045095  lea     r9, [rbp+57h+var_90]
0x180045099  lea     r8, [rbp+57h+var_70]
0x18004509d  mov     rdx, [rdx+20h]
0x1800450a1  mov     rax, [rax+28h]
0x1800450a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450aa  mov     ebx, eax
0x1800450ac  lea     rcx, [rbp+57h+var_90]
0x1800450b0  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800450b5  mov     ecx, dword ptr [rbp+57h+var_A0]; this
0x1800450b8  test    ecx, ecx
0x1800450ba  jns     short loc_1800450C2
0x1800450bc  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800450c2  test    ebx, ebx
0x1800450c4  jns     short loc_1800450CE
0x1800450c6  mov     ecx, ebx; this
0x1800450c8  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800450ce  lea     rcx, [rbp+57h+var_70]; this
0x1800450d2  call    ??0D2DImageData@xpsrdr@@QEAA@XZ; xpsrdr::D2DImageData::D2DImageData(void)
0x1800450d7  nop
0x1800450d8  mov     rdx, rdi
0x1800450db  lea     rcx, [rbp+57h+var_70]
0x1800450df  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800450e4  mov     rax, [rsi+30h]
0x1800450e8  movss   xmm7, dword ptr [rax+0Ch]
0x1800450ed  movss   [rbp+57h+var_60], xmm7
0x1800450f2  movss   xmm6, dword ptr [rax+8]
0x1800450f7  movss   [rbp+57h+var_5C], xmm6
0x1800450fc  mov     rcx, [rsi+20h]
0x180045100  add     rcx, r12
0x180045103  mov     rdx, [r14]
0x180045106  call    ??A?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAAAEAUD2DImageData@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::operator[](std::wstring const &)
0x18004510b  mov     rbx, rax
0x18004510e  lea     rdx, [rbp+57h+var_70]
0x180045112  mov     rcx, rax
0x180045115  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x18004511a  movss   dword ptr [rbx+10h], xmm7
0x18004511f  movss   dword ptr [rbx+14h], xmm6
0x180045124  lea     rcx, [rbp+57h+var_70]
0x180045128  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18004512d  mov     rax, rdi
0x180045130  mov     rcx, [rbp+57h+var_58]
0x180045134  xor     rcx, rsp; StackCookie
0x180045137  call    __security_check_cookie
0x18004513c  lea     r11, [rsp+0D0h+var_28]
0x180045144  movaps  xmm6, xmmword ptr [r11-18h]
0x180045149  movaps  xmm7, xmmword ptr [r11-28h]
0x18004514e  mov     rsp, r11
0x180045151  pop     r14
0x180045153  pop     r12
0x180045155  pop     rdi
0x180045156  pop     rsi
0x180045157  pop     rbx
0x180045158  pop     rbp
0x180045159  retn
```
