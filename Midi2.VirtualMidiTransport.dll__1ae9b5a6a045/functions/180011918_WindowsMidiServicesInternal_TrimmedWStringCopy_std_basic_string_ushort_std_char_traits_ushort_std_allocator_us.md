# WindowsMidiServicesInternal::TrimmedWStringCopy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180011918`
- end: `0x180011983`
- name: `?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `107`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000d8e8`
- `0x18000e0a4`
- `0x1800116e0`
- `0x1800117d8`

## callees

- `0x1800038f0`
- `0x18000bf6c`
- `0x18000d1ac`
- `0x180010954`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
wchar_t *__fastcall WindowsMidiServicesInternal::TrimmedWStringCopy(wchar_t *Src, __int64 a2)
{
  std::wstring::wstring(Src, a2);
  WindowsMidiServicesInternal::InPlaceTrim(Src);
  std::wstring::~wstring(a2);
  return Src;
}

```

## disassembly

```asm
0x180011918  mov     [rsp+arg_10], rbx
0x18001191d  push    rdi
0x18001191e  sub     rsp, 40h
0x180011922  mov     rax, cs:__security_cookie
0x180011929  xor     rax, rsp
0x18001192c  mov     [rsp+48h+var_10], rax
0x180011931  mov     rdi, rdx
0x180011934  mov     rbx, rcx
0x180011937  mov     [rsp+48h+var_20], rcx
0x18001193c  mov     [rsp+48h+var_18], rdx
0x180011941  mov     [rsp+48h+var_28], 0
0x180011949  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001194e  mov     [rsp+48h+var_28], 1
0x180011956  mov     rcx, rbx; Src
0x180011959  call    ?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::InPlaceTrim(std::wstring &)
0x18001195e  nop
0x18001195f  mov     rcx, rdi
0x180011962  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011967  mov     rax, rbx
0x18001196a  mov     rcx, [rsp+48h+var_10]
0x18001196f  xor     rcx, rsp; StackCookie
0x180011972  call    __security_check_cookie
0x180011977  mov     rbx, [rsp+48h+arg_10]
0x18001197c  add     rsp, 40h
0x180011980  pop     rdi
0x180011981  retn
```
