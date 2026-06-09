# xpsrdr::TileBrushBuilder::CreateBitmapFromWicBitmap(std::shared_ptr<xpsrdr::Image> const &,std::shared_ptr<ID2D1DeviceContext> &)

- ea: `0x1800bbabc`
- end: `0x1800bbc97`
- name: `?CreateBitmapFromWicBitmap@TileBrushBuilder@xpsrdr@@AEAA?AV?$shared_ptr@UID2D1Bitmap@@@std@@AEBV?$shared_ptr@UImage@xpsrdr@@@4@AEAV?$shared_ptr@UID2D1DeviceContext@@@4@@Z`
- size: `475`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800bbca0`

## callees

- `0x180003180`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800adcc0`
- `0x1800b20e8`
- `0x1800ba76c`
- `0x1800bb6e4`
- `0x1800bbabc`
- `0x1800c3010`

## pseudocode

```c
_QWORD *__fastcall xpsrdr::TileBrushBuilder::CreateBitmapFromWicBitmap(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 *a4)
{
  std::_Ref_count_base *v8; // rbx
  float v9; // xmm0_4
  float v10; // xmm0_4
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  __int64 v17; // rax
  int v18; // xmm7_4
  int v19; // xmm6_4
  __int64 v20; // rbx
  xpsrdr *v22; // [rsp+38h] [rbp-49h] BYREF
  _QWORD v23[4]; // [rsp+40h] [rbp-41h] BYREF
  std::_Ref_count_base *v24[2]; // [rsp+60h] [rbp-21h] BYREF
  int v25; // [rsp+70h] [rbp-11h]
  int v26; // [rsp+74h] [rbp-Dh]

  v23[3] = a2;
  *a2 = 0;
  a2[1] = 0;
  HIDWORD(v22) = 1;
  xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::find(
    *(_QWORD *)(a1 + 32) + 320LL,
    v24,
    *a3);
  v8 = v24[0];
  if ( v24[0] == *(std::_Ref_count_base **)(*(_QWORD *)(a1 + 32) + 328LL) )
  {
    LODWORD(v22) = 0;
    v11 = *a4;
    v23[0] = 0;
    v23[1] = &v22;
    v23[2] = a2;
    v12 = *a3;
    v24[0] = 0;
    v24[1] = *(std::_Ref_count_base **)(v12 + 60);
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, std::_Ref_count_base **, _QWORD *))(*(_QWORD *)v11 + 40LL))(
            v11,
            *(_QWORD *)(v12 + 32),
            v24,
            v23);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v23);
    if ( (int)v22 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v14, v15, v16);
    if ( v13 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
    *(_OWORD *)v24 = 0;
    std::shared_ptr<ID2D1Brush>::operator=(v24, a2);
    v17 = *(_QWORD *)(a1 + 48);
    v25 = *(_DWORD *)(v17 + 12);
    v18 = v25;
    v26 = *(_DWORD *)(v17 + 8);
    v19 = v26;
    v20 = xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::operator[](
            *(_QWORD *)(a1 + 32) + 320LL,
            *a3);
    std::shared_ptr<ID2D1Brush>::operator=(v20, v24);
    *(_DWORD *)(v20 + 16) = v18;
    *(_DWORD *)(v20 + 20) = v19;
    if ( v24[1] )
      std::_Ref_count_base::_Decref(v24[1]);
  }
  else
  {
    std::shared_ptr<ID2D1Brush>::operator=(a2, (char *)v24[0] + 48);
    v9 = *(float *)(*(_QWORD *)(a1 + 48) + 12LL);
    if ( v9 > *((float *)v8 + 16) )
      *((float *)v8 + 16) = v9;
    v10 = *(float *)(*(_QWORD *)(a1 + 48) + 8LL);
    if ( v10 > *((float *)v8 + 17) )
      *((float *)v8 + 17) = v10;
  }
  return a2;
}

```

## disassembly

```asm
0x1800bbabc  mov     rax, rsp
0x1800bbabf  push    rbp
0x1800bbac0  push    rbx
0x1800bbac1  push    rsi
0x1800bbac2  push    rdi
0x1800bbac3  push    r14
0x1800bbac5  push    r15
0x1800bbac7  lea     rbp, [rax-5Fh]
0x1800bbacb  sub     rsp, 0A8h
0x1800bbad2  movaps  xmmword ptr [rax-48h], xmm6
0x1800bbad6  movaps  xmmword ptr [rax-58h], xmm7
0x1800bbada  mov     rax, cs:__security_cookie
0x1800bbae1  xor     rax, rsp
0x1800bbae4  mov     [rbp+57h+var_60], rax
0x1800bbae8  mov     r15, r9
0x1800bbaeb  mov     r14, r8
0x1800bbaee  mov     rdi, rdx
0x1800bbaf1  mov     rsi, rcx
0x1800bbaf4  mov     [rbp+57h+var_80], rdx
0x1800bbaf8  mov     dword ptr [rbp+57h+var_A0+4], 0
0x1800bbaff  mov     qword ptr [rdx], 0
0x1800bbb06  mov     qword ptr [rdx+8], 0
0x1800bbb0e  mov     dword ptr [rbp+57h+var_A0+4], 1
0x1800bbb15  mov     rcx, [rcx+20h]
0x1800bbb19  add     rcx, 140h
0x1800bbb20  mov     r8, [r8]
0x1800bbb23  lea     rdx, [rbp+57h+var_78]
0x1800bbb27  call    ?find@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::find(std::wstring const &)
0x1800bbb2c  mov     rax, [rsi+20h]
0x1800bbb30  mov     rbx, [rbp+57h+var_78]
0x1800bbb34  cmp     rbx, [rax+148h]
0x1800bbb3b  jz      short loc_1800BBB7A
0x1800bbb3d  lea     rdx, [rbx+30h]
0x1800bbb41  mov     rcx, rdi
0x1800bbb44  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800bbb49  mov     rax, [rsi+30h]
0x1800bbb4d  movss   xmm0, dword ptr [rax+0Ch]
0x1800bbb52  comiss  xmm0, dword ptr [rbx+40h]
0x1800bbb56  jbe     short loc_1800BBB5D
0x1800bbb58  movss   dword ptr [rbx+40h], xmm0
0x1800bbb5d  mov     rax, [rsi+30h]
0x1800bbb61  movss   xmm0, dword ptr [rax+8]
0x1800bbb66  comiss  xmm0, dword ptr [rbx+44h]
0x1800bbb6a  jbe     loc_1800BBC69
0x1800bbb70  movss   dword ptr [rbx+44h], xmm0
0x1800bbb75  jmp     loc_1800BBC69
0x1800bbb7a  mov     dword ptr [rbp+57h+var_A0], 0
0x1800bbb81  mov     rcx, [r15]
0x1800bbb84  mov     [rbp+57h+var_98], 0
0x1800bbb8c  lea     rax, [rbp+57h+var_A0]
0x1800bbb90  mov     [rbp+57h+var_90], rax
0x1800bbb94  mov     [rbp+57h+var_88], rdi
0x1800bbb98  mov     rdx, [r14]
0x1800bbb9b  mov     [rbp+57h+var_78], 0
0x1800bbba3  mov     rax, [rbp+57h+var_78]
0x1800bbba7  mov     [rbp+57h+var_78], rax
0x1800bbbab  movss   xmm0, dword ptr [rdx+3Ch]
0x1800bbbb0  movss   dword ptr [rbp+57h+var_78+8], xmm0
0x1800bbbb5  movss   xmm1, dword ptr [rdx+40h]
0x1800bbbba  movss   dword ptr [rbp+57h+var_78+0Ch], xmm1
0x1800bbbbf  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x1800bbbc3  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x1800bbbc7  mov     rax, [rcx]
0x1800bbbca  lea     r9, [rbp+57h+var_98]
0x1800bbbce  lea     r8, [rbp+57h+var_78]
0x1800bbbd2  mov     rdx, [rdx+20h]
0x1800bbbd6  mov     rax, [rax+28h]
0x1800bbbda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbbdf  mov     ebx, eax
0x1800bbbe1  lea     rcx, [rbp+57h+var_98]
0x1800bbbe5  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bbbea  mov     ecx, dword ptr [rbp+57h+var_A0]; this
0x1800bbbed  test    ecx, ecx
0x1800bbbef  jns     short loc_1800BBBF7
0x1800bbbf1  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bbbf7  test    ebx, ebx
0x1800bbbf9  jns     short loc_1800BBC03
0x1800bbbfb  mov     ecx, ebx; this
0x1800bbbfd  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bbc03  xorps   xmm0, xmm0
0x1800bbc06  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x1800bbc0b  mov     rdx, rdi
0x1800bbc0e  lea     rcx, [rbp+57h+var_78]
0x1800bbc12  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800bbc17  mov     rax, [rsi+30h]
0x1800bbc1b  movss   xmm7, dword ptr [rax+0Ch]
0x1800bbc20  movss   [rbp+57h+var_68], xmm7
0x1800bbc25  movss   xmm6, dword ptr [rax+8]
0x1800bbc2a  movss   [rbp+57h+var_64], xmm6
0x1800bbc2f  mov     rcx, [rsi+20h]
0x1800bbc33  add     rcx, 140h
0x1800bbc3a  mov     rdx, [r14]
0x1800bbc3d  call    ??A?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAAAEAUD2DImageData@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::operator[](std::wstring const &)
0x1800bbc42  mov     rbx, rax
0x1800bbc45  lea     rdx, [rbp+57h+var_78]
0x1800bbc49  mov     rcx, rax
0x1800bbc4c  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800bbc51  movss   dword ptr [rbx+10h], xmm7
0x1800bbc56  movss   dword ptr [rbx+14h], xmm6
0x1800bbc5b  mov     rcx, [rbp+57h+var_78+8]; this
0x1800bbc5f  test    rcx, rcx
0x1800bbc62  jz      short loc_1800BBC69
0x1800bbc64  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bbc69  mov     rax, rdi
0x1800bbc6c  mov     rcx, [rbp+57h+var_60]
0x1800bbc70  xor     rcx, rsp; StackCookie
0x1800bbc73  call    __security_check_cookie
0x1800bbc78  lea     r11, [rsp+0D0h+var_28]
0x1800bbc80  movaps  xmm6, xmmword ptr [r11-18h]
0x1800bbc85  movaps  xmm7, xmmword ptr [r11-28h]
0x1800bbc8a  mov     rsp, r11
0x1800bbc8d  pop     r15
0x1800bbc8f  pop     r14
0x1800bbc91  pop     rdi
0x1800bbc92  pop     rsi
0x1800bbc93  pop     rbx
0x1800bbc94  pop     rbp
0x1800bbc95  retn
```
