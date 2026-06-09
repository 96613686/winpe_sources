# xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::operator[](xpsrdr::KeyBrush const &)

- ea: `0x18003feb0`
- end: `0x18003ff74`
- name: `??A?$Cache@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@U?$Hash@UKeyBrush@xpsrdr@@@2@U?$Weight@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@2@@xpsrdr@@QEAAAEAU?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@AEBUKeyBrush@1@@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180040014`

## callees

- `0x180008830`
- `0x1800122a8`
- `0x18001df50`
- `0x1800229e8`
- `0x18003fb60`
- `0x18003fc14`
- `0x18003feb0`
- `0x180041a30`
- `0x180041ae4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::operator[](
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // r8
  _QWORD *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v9; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v10[16]; // [rsp+28h] [rbp-B0h] BYREF
  _BYTE v11[40]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v12[56]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v13[40]; // [rsp+98h] [rbp-40h] BYREF

  xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::find(
    a1,
    &v9,
    a2);
  v5 = (_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                   a1,
                   (__int64)v10,
                   v4);
  if ( v9 == *v5 )
  {
    v6 = std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v11);
    v7 = std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>(
           v12,
           a2,
           v6);
    v9 = *(_QWORD *)xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::insert(
                      a1,
                      (__int64)v10,
                      v7);
    std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v13);
    std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v11);
  }
  return std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(&v9)
       + 56;
}

```

## disassembly

```asm
0x18003feb0  mov     [rsp+arg_10], rbx
0x18003feb5  push    rdi
0x18003feb6  sub     rsp, 0D0h
0x18003febd  mov     rax, cs:__security_cookie
0x18003fec4  xor     rax, rsp
0x18003fec7  mov     [rsp+0D8h+var_18], rax
0x18003fecf  mov     rdi, rdx
0x18003fed2  mov     rbx, rcx
0x18003fed5  mov     r8, rdx
0x18003fed8  lea     rdx, [rsp+0D8h+var_B8]
0x18003fedd  call    ?find@?$Cache@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@U?$Hash@UKeyBrush@xpsrdr@@@2@U?$Weight@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@2@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@@std@@@std@@@std@@AEBUKeyBrush@2@@Z; xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::find(xpsrdr::KeyBrush const &)
0x18003fee2  lea     rdx, [rsp+0D8h+var_B0]
0x18003fee7  mov     rcx, rbx
0x18003feea  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x18003feef  mov     rcx, [rax]
0x18003fef2  cmp     [rsp+0D8h+var_B8], rcx
0x18003fef7  jnz     short loc_18003FF45
0x18003fef9  lea     rcx, [rsp+0D8h+var_A0]
0x18003fefe  call    ??$?0V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@1@$0A@@?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@XZ; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(void)
0x18003ff03  nop
0x18003ff04  mov     r8, rax
0x18003ff07  mov     rdx, rdi
0x18003ff0a  lea     rcx, [rsp+0D8h+var_78]
0x18003ff0f  call    ??$?0AEBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@$0A@@?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@QEAA@AEBUKeyBrush@xpsrdr@@$$QEAU?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@1@@Z; std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>(xpsrdr::KeyBrush const &,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>> &&)
0x18003ff14  nop
0x18003ff15  mov     r8, rax
0x18003ff18  lea     rdx, [rsp+0D8h+var_B0]
0x18003ff1d  mov     rcx, rbx
0x18003ff20  call    ?insert@?$Cache@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@U?$Hash@UKeyBrush@xpsrdr@@@2@U?$Weight@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@2@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@4@@Z; xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::insert(std::pair<xpsrdr::KeyBrush const,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>> const &)
0x18003ff25  mov     rcx, [rax]
0x18003ff28  mov     [rsp+0D8h+var_B8], rcx
0x18003ff2d  lea     rcx, [rsp+0D8h+var_40]
0x18003ff35  call    ??1?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@XZ; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(void)
0x18003ff3a  nop
0x18003ff3b  lea     rcx, [rsp+0D8h+var_A0]
0x18003ff40  call    ??1?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@XZ; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(void)
0x18003ff45  lea     rcx, [rsp+0D8h+var_B8]
0x18003ff4a  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x18003ff4f  add     rax, 38h ; '8'
0x18003ff53  mov     rcx, [rsp+0D8h+var_18]
0x18003ff5b  xor     rcx, rsp; StackCookie
0x18003ff5e  call    __security_check_cookie
0x18003ff63  mov     rbx, [rsp+0D8h+arg_10]
0x18003ff6b  add     rsp, 0D0h
0x18003ff72  pop     rdi
0x18003ff73  retn
```
