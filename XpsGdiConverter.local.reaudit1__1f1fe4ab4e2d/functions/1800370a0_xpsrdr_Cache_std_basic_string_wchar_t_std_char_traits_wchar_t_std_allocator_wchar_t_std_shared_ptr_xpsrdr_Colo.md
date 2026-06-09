# xpsrdr::Cache<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,xpsrdr::Weight<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::ColorContext>>>::resize(float)

- ea: `0x1800370a0`
- end: `0x180037127`
- name: `?resize@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAAXM@Z`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180036f00`

## callees

- `0x180008830`
- `0x18000e5ec`
- `0x18001cef8`
- `0x1800228dc`
- `0x1800231f4`
- `0x180036d44`
- `0x1800370a0`
- `0x1800372e4`

## pseudocode

```c
float __fastcall xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::resize(
        xpsrdr *a1,
        const char *a2,
        int a3)
{
  float v3; // xmm1_4
  float *v4; // rbx
  __int64 v5; // rax
  float result; // xmm0_4
  _BYTE v7[32]; // [rsp+20h] [rbp-38h] BYREF

  v4 = (float *)a1;
  if ( v3 < 0.0 )
    xpsrdr::ThrowLogicException(a1, a2, a3);
  *(float *)a1 = v3;
  while ( 1 )
  {
    result = xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::weight(a1);
    if ( result <= v3 )
      break;
    v5 = std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>::back(v4 + 2);
    std::wstring::wstring(v7, v5);
    xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::erase(
      (__int64)v4,
      (__int64)v7);
    std::wstring::~wstring(v7);
    v3 = *v4;
    a1 = (xpsrdr *)v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800370a0  mov     [rsp+arg_8], rbx
0x1800370a5  push    rdi
0x1800370a6  sub     rsp, 50h
0x1800370aa  mov     rax, cs:__security_cookie
0x1800370b1  xor     rax, rsp
0x1800370b4  mov     [rsp+58h+var_18], rax
0x1800370b9  comiss  xmm1, cs:__real@00000000
0x1800370c0  mov     rbx, rcx
0x1800370c3  jnb     short loc_1800370CB
0x1800370c5  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800370cb  movss   dword ptr [rcx], xmm1
0x1800370cf  jmp     short loc_180037105
0x1800370d1  lea     rcx, [rbx+8]
0x1800370d5  call    ?back@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@2@@std@@QEAAAEAU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@2@XZ; std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>::back(void)
0x1800370da  mov     rdx, rax
0x1800370dd  lea     rcx, [rsp+58h+var_38]
0x1800370e2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800370e7  lea     rdx, [rsp+58h+var_38]
0x1800370ec  mov     rcx, rbx
0x1800370ef  call    ?erase@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::erase(std::wstring const &)
0x1800370f4  lea     rcx, [rsp+58h+var_38]
0x1800370f9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800370fe  movss   xmm1, dword ptr [rbx]
0x180037102  mov     rcx, rbx
0x180037105  call    ?weight@?$Cache@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@U?$Hash@UKeyFontFace@xpsrdr@@@2@U?$Weight@UKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@2@@xpsrdr@@QEBAMXZ; xpsrdr::Cache<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>,xpsrdr::Hash<xpsrdr::KeyFontFace>,xpsrdr::Weight<xpsrdr::KeyFontFace,std::shared_ptr<IDWriteFontFace>>>::weight(void)
0x18003710a  comiss  xmm0, xmm1
0x18003710d  ja      short loc_1800370D1
0x18003710f  mov     rcx, [rsp+58h+var_18]
0x180037114  xor     rcx, rsp; StackCookie
0x180037117  call    __security_check_cookie
0x18003711c  mov     rbx, [rsp+58h+arg_8]
0x180037121  add     rsp, 50h
0x180037125  pop     rdi
0x180037126  retn
```
