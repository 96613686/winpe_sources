# xpsrdr::VisualsRasterizer::ClearBitmapCacheForBand(uint,uint)

- ea: `0x180037aa8`
- end: `0x180037b9c`
- name: `?ClearBitmapCacheForBand@VisualsRasterizer@xpsrdr@@AEAAXII@Z`
- size: `244`
- prototype: `void __fastcall(xpsrdr::VisualsRasterizer *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180038804`
- `0x18003890c`

## callees

- `0x18000e174`
- `0x18001df50`
- `0x1800229e8`
- `0x180037940`
- `0x180037aa8`
- `0x18003b48c`
- `0x18003b4dc`
- `0x18003b650`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall xpsrdr::VisualsRasterizer::ClearBitmapCacheForBand(xpsrdr::VisualsRasterizer *this, __int64 a2, int a3)
{
  int v4; // esi
  __int64 v6; // r8
  _QWORD *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rax
  unsigned __int64 v10; // rbx
  __int64 j; // rcx
  __int64 v12; // [rsp+20h] [rbp-20h] BYREF
  __int64 v13; // [rsp+28h] [rbp-18h]
  __int64 i; // [rsp+60h] [rbp+20h] BYREF
  char v15; // [rsp+78h] [rbp+38h] BYREF

  v4 = a2;
  std::vector<CCoordinate>::vector<CCoordinate>(&v12, a2);
  for ( i = **(_QWORD **)(*(_QWORD *)this + 328LL);
        ;
        std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>::operator++(&i) )
  {
    v7 = (_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                     *(_QWORD *)this + 320LL,
                     (__int64)&v15,
                     v6);
    if ( v8 == *v7 )
      break;
    v9 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(&i);
    if ( (float)v4 <= *(float *)(v9 + 48) || (float)a3 <= *(float *)(v9 + 52) && a3 )
      *(_QWORD *)(v9 + 48) = 0;
    else
      std::vector<std::wstring>::push_back(&v12, v9);
  }
  v10 = 0;
  for ( j = v12; v10 < (v13 - v12) >> 5; j = v12 )
    xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::erase(
      *(_QWORD *)this + 320LL,
      j + 32 * v10++);
  std::vector<std::wstring>::_Tidy(&v12);
}

```

## disassembly

```asm
0x180037aa8  mov     [rsp-18h+arg_8], rbx
0x180037aad  push    rbp
0x180037aae  push    rsi
0x180037aaf  push    rdi
0x180037ab0  mov     rbp, rsp
0x180037ab3  sub     rsp, 40h
0x180037ab7  mov     ebx, r8d
0x180037aba  mov     esi, edx
0x180037abc  mov     rdi, rcx
0x180037abf  lea     rcx, [rbp+var_20]
0x180037ac3  call    ??0?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::vector<CCoordinate>(void)
0x180037ac8  nop
0x180037ac9  mov     rax, [rdi]
0x180037acc  mov     r9, [rax+148h]
0x180037ad3  mov     r9, [r9]
0x180037ad6  mov     [rbp+arg_0], r9
0x180037ada  mov     rcx, [rdi]
0x180037add  add     rcx, 140h
0x180037ae4  lea     rdx, [rbp+arg_18]
0x180037ae8  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x180037aed  cmp     r9, [rax]
0x180037af0  jz      short loc_180037B40
0x180037af2  lea     rcx, [rbp+arg_0]
0x180037af6  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180037afb  xorps   xmm0, xmm0
0x180037afe  cvtsi2ss xmm0, rsi
0x180037b03  comiss  xmm0, dword ptr [rax+30h]
0x180037b07  jbe     short loc_180037B29
0x180037b09  xorps   xmm0, xmm0
0x180037b0c  cvtsi2ss xmm0, rbx
0x180037b11  comiss  xmm0, dword ptr [rax+34h]
0x180037b15  ja      short loc_180037B1B
0x180037b17  test    ebx, ebx
0x180037b19  jnz     short loc_180037B29
0x180037b1b  mov     rdx, rax
0x180037b1e  lea     rcx, [rbp+var_20]
0x180037b22  call    ?push_back@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x180037b27  jmp     short loc_180037B31
0x180037b29  mov     qword ptr [rax+30h], 0
0x180037b31  lea     rcx, [rbp+arg_0]
0x180037b35  call    ??E?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>::operator++(void)
0x180037b3a  mov     r9, [rbp+arg_0]
0x180037b3e  jmp     short loc_180037ADA
0x180037b40  xor     ebx, ebx
0x180037b42  mov     rcx, [rbp+var_20]
0x180037b46  mov     rax, [rbp+var_18]
0x180037b4a  sub     rax, rcx
0x180037b4d  sar     rax, 5
0x180037b51  test    rax, rax
0x180037b54  jz      short loc_180037B86
0x180037b56  mov     rdx, rbx
0x180037b59  shl     rdx, 5
0x180037b5d  add     rdx, rcx
0x180037b60  mov     rcx, [rdi]
0x180037b63  add     rcx, 140h
0x180037b6a  call    ?erase@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::erase(std::wstring const &)
0x180037b6f  inc     rbx
0x180037b72  mov     rcx, [rbp+var_20]
0x180037b76  mov     rax, [rbp+var_18]
0x180037b7a  sub     rax, rcx
0x180037b7d  sar     rax, 5
0x180037b81  cmp     rbx, rax
0x180037b84  jb      short loc_180037B56
0x180037b86  lea     rcx, [rbp+var_20]
0x180037b8a  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180037b8f  mov     rbx, [rsp+40h+arg_8]
0x180037b94  add     rsp, 40h
0x180037b98  pop     rdi
0x180037b99  pop     rsi
0x180037b9a  pop     rbp
0x180037b9b  retn
```
