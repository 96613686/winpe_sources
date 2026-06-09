# WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800117d8`
- end: `0x180011850`
- name: `?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `120`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000d9b4`
- `0x18000e0a4`
- `0x18000e840`
- `0x18000eae0`
- `0x18000ec98`
- `0x180014ab0`
- `0x1800159c8`

## callees

- `0x1800038f0`
- `0x18000bf6c`
- `0x18000d1ac`
- `0x180011858`
- `0x180011918`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  _BYTE v6[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE Src[32]; // [rsp+50h] [rbp-38h] BYREF
  __int64 v8; // [rsp+70h] [rbp-18h]

  v8 = a2;
  std::wstring::wstring(v6, a2);
  v4 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src);
  WindowsMidiServicesInternal::ToUpperWStringCopy(a1, v4);
  std::wstring::~wstring(a2);
  return a1;
}

```

## disassembly

```asm
0x1800117d8  mov     [rsp+arg_10], rbx
0x1800117dd  push    rdi
0x1800117de  sub     rsp, 80h
0x1800117e5  mov     rax, cs:__security_cookie
0x1800117ec  xor     rax, rsp
0x1800117ef  mov     [rsp+88h+var_10], rax
0x1800117f4  mov     rdi, rdx
0x1800117f7  mov     rbx, rcx
0x1800117fa  mov     [rsp+88h+var_18], rcx
0x1800117ff  mov     [rsp+88h+var_18], rdx
0x180011804  lea     rcx, [rsp+88h+var_58]
0x180011809  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001180e  mov     rdx, rax
0x180011811  lea     rcx, [rsp+88h+Src]; Src
0x180011816  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18001181b  mov     rdx, rax
0x18001181e  mov     rcx, rbx
0x180011821  call    ?ToUpperWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperWStringCopy(std::wstring)
0x180011826  nop
0x180011827  mov     rcx, rdi
0x18001182a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001182f  mov     rax, rbx
0x180011832  mov     rcx, [rsp+88h+var_10]
0x180011837  xor     rcx, rsp; StackCookie
0x18001183a  call    __security_check_cookie
0x18001183f  mov     rbx, [rsp+88h+arg_10]
0x180011847  add     rsp, 80h
0x18001184e  pop     rdi
0x18001184f  retn
```
