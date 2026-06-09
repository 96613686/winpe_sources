# xpsrdr::Cache<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,xpsrdr::Weight<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::Image>>>::resize(float)

- ea: `0x18003f4e4`
- end: `0x18003f578`
- name: `?resize@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@5@@xpsrdr@@QEAAXM@Z`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003f3d0`

## callees

- `0x180008830`
- `0x18000e5ec`
- `0x18001cef8`
- `0x1800228dc`
- `0x180036d44`
- `0x1800372e4`
- `0x18003f4e4`
- `0x18003f580`

## pseudocode

```c
float __fastcall xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::resize(
        xpsrdr *a1,
        const char *a2,
        int a3)
{
  float v3; // xmm1_4
  float *v4; // rbx
  float v5; // xmm6_4
  __int64 v6; // rax
  float result; // xmm0_4
  _BYTE v8[32]; // [rsp+20h] [rbp-48h] BYREF

  v4 = (float *)a1;
  if ( v3 < 0.0 )
    xpsrdr::ThrowLogicException(a1, a2, a3);
  *(float *)a1 = v3;
  v5 = v3;
  while ( 1 )
  {
    result = xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::weight(a1);
    if ( result <= v5 )
      break;
    v6 = std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>::back(v4 + 2);
    std::wstring::wstring(v8, v6);
    xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::erase(
      (__int64)v4,
      (__int64)v8);
    std::wstring::~wstring(v8);
    v5 = *v4;
    a1 = (xpsrdr *)v4;
  }
  return result;
}

```

## disassembly

```asm
0x18003f4e4  mov     [rsp+arg_8], rbx
0x18003f4e9  push    rdi
0x18003f4ea  sub     rsp, 60h
0x18003f4ee  movaps  [rsp+68h+var_18], xmm6
0x18003f4f3  mov     rax, cs:__security_cookie
0x18003f4fa  xor     rax, rsp
0x18003f4fd  mov     [rsp+68h+var_28], rax
0x18003f502  comiss  xmm1, cs:__real@00000000
0x18003f509  mov     rbx, rcx
0x18003f50c  jnb     short loc_18003F514
0x18003f50e  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003f514  movss   dword ptr [rcx], xmm1
0x18003f518  movaps  xmm6, xmm1
0x18003f51b  jmp     short loc_18003F551
0x18003f51d  lea     rcx, [rbx+8]
0x18003f521  call    ?back@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@2@@std@@QEAAAEAU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@2@XZ; std::list<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>::back(void)
0x18003f526  mov     rdx, rax
0x18003f529  lea     rcx, [rsp+68h+var_48]
0x18003f52e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003f533  lea     rdx, [rsp+68h+var_48]
0x18003f538  mov     rcx, rbx
0x18003f53b  call    ?erase@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::erase(std::wstring const &)
0x18003f540  lea     rcx, [rsp+68h+var_48]
0x18003f545  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003f54a  movss   xmm6, dword ptr [rbx]
0x18003f54e  mov     rcx, rbx
0x18003f551  call    ?weight@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@5@@xpsrdr@@QEBAMXZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::weight(void)
0x18003f556  comiss  xmm0, xmm6
0x18003f559  ja      short loc_18003F51D
0x18003f55b  mov     rcx, [rsp+68h+var_28]
0x18003f560  xor     rcx, rsp; StackCookie
0x18003f563  call    __security_check_cookie
0x18003f568  mov     rbx, [rsp+68h+arg_8]
0x18003f56d  movaps  xmm6, [rsp+68h+var_18]
0x18003f572  add     rsp, 60h
0x18003f576  pop     rdi
0x18003f577  retn
```
