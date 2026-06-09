# WindowsMidiServicesInternal::TrimmedWStringCopy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800134cc`
- end: `0x180013537`
- name: `?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `107`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `8`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180013294`
- `0x18001338c`
- `0x18001d454`
- `0x18002bda8`
- `0x18002c0e0`
- `0x18002c41c`
- `0x18002c688`
- `0x18002cce0`

## callees

- `0x180004180`
- `0x18000b740`
- `0x18000f0a4`
- `0x180011620`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
wchar_t *__fastcall WindowsMidiServicesInternal::TrimmedWStringCopy(wchar_t *Src, void *a2)
{
  std::wstring::wstring(Src, a2);
  WindowsMidiServicesInternal::InPlaceTrim(Src);
  std::wstring::~wstring(a2);
  return Src;
}

```

## disassembly

```asm
0x1800134cc  mov     [rsp+arg_10], rbx
0x1800134d1  push    rdi
0x1800134d2  sub     rsp, 40h
0x1800134d6  mov     rax, cs:__security_cookie
0x1800134dd  xor     rax, rsp
0x1800134e0  mov     [rsp+48h+var_10], rax
0x1800134e5  mov     rdi, rdx
0x1800134e8  mov     rbx, rcx
0x1800134eb  mov     [rsp+48h+var_20], rcx
0x1800134f0  mov     [rsp+48h+var_18], rdx
0x1800134f5  mov     [rsp+48h+var_28], 0
0x1800134fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180013502  mov     [rsp+48h+var_28], 1
0x18001350a  mov     rcx, rbx; Src
0x18001350d  call    ?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WindowsMidiServicesInternal::InPlaceTrim(std::wstring &)
0x180013512  nop
0x180013513  mov     rcx, rdi; void *
0x180013516  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001351b  mov     rax, rbx
0x18001351e  mov     rcx, [rsp+48h+var_10]
0x180013523  xor     rcx, rsp; StackCookie
0x180013526  call    __security_check_cookie
0x18001352b  mov     rbx, [rsp+48h+arg_10]
0x180013530  add     rsp, 40h
0x180013534  pop     rdi
0x180013535  retn
```
