# WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001338c`
- end: `0x180013404`
- name: `?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180011980`
- `0x18001d188`
- `0x18001d454`
- `0x18002c0e0`

## callees

- `0x180004180`
- `0x18000b740`
- `0x18000f0a4`
- `0x18001340c`
- `0x1800134cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(__int64 a1, void *a2)
{
  void *v4; // rax
  wchar_t *v5; // rax
  _BYTE v7[32]; // [rsp+30h] [rbp-58h] BYREF
  wchar_t Src[16]; // [rsp+50h] [rbp-38h] BYREF
  void *v9; // [rsp+70h] [rbp-18h]

  v9 = a2;
  v4 = (void *)std::wstring::wstring(v7, a2);
  v5 = WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v4);
  WindowsMidiServicesInternal::ToUpperWStringCopy(a1, v5);
  std::wstring::~wstring(a2);
  return a1;
}

```

## disassembly

```asm
0x18001338c  mov     [rsp+arg_10], rbx
0x180013391  push    rdi
0x180013392  sub     rsp, 80h
0x180013399  mov     rax, cs:__security_cookie
0x1800133a0  xor     rax, rsp
0x1800133a3  mov     [rsp+88h+var_10], rax
0x1800133a8  mov     rdi, rdx
0x1800133ab  mov     rbx, rcx
0x1800133ae  mov     [rsp+88h+var_18], rcx
0x1800133b3  mov     [rsp+88h+var_18], rdx
0x1800133b8  lea     rcx, [rsp+88h+var_58]
0x1800133bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800133c2  mov     rdx, rax; void *
0x1800133c5  lea     rcx, [rsp+88h+Src]; Src
0x1800133ca  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x1800133cf  mov     rdx, rax
0x1800133d2  mov     rcx, rbx
0x1800133d5  call    ?ToUpperWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperWStringCopy(std::wstring)
0x1800133da  nop
0x1800133db  mov     rcx, rdi; void *
0x1800133de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800133e3  mov     rax, rbx
0x1800133e6  mov     rcx, [rsp+88h+var_10]
0x1800133eb  xor     rcx, rsp; StackCookie
0x1800133ee  call    __security_check_cookie
0x1800133f3  mov     rbx, [rsp+88h+arg_10]
0x1800133fb  add     rsp, 80h
0x180013402  pop     rdi
0x180013403  retn
```
