# WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000d8e8`
- end: `0x18000d9ad`
- name: `?CalculateEndpointDevicePrimaryName@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00@Z`
- size: `197`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000d9b4`
- `0x18000e0a4`

## callees

- `0x1800038f0`
- `0x18000bf6c`
- `0x18000d1ac`
- `0x18000d8e8`
- `0x180011918`

## pseudocode

```c
void *__fastcall WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName(
        void *Src,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rbx
  _BYTE Srca[32]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v13[32]; // [rsp+50h] [rbp-9h] BYREF

  std::wstring::wstring(v13, a3);
  v8 = *(_QWORD *)(WindowsMidiServicesInternal::TrimmedWStringCopy(Srca) + 16);
  std::wstring::~wstring(Srca);
  if ( v8 )
  {
    v9 = a3;
  }
  else
  {
    std::wstring::wstring(Srca, a4);
    v10 = *(_QWORD *)(WindowsMidiServicesInternal::TrimmedWStringCopy(v13) + 16);
    std::wstring::~wstring(v13);
    v9 = a4;
    if ( !v10 )
      v9 = a2;
  }
  std::wstring::wstring(Srca, v9);
  WindowsMidiServicesInternal::TrimmedWStringCopy(Src);
  return Src;
}

```

## disassembly

```asm
0x18000d8e8  push    rbp
0x18000d8ea  push    rbx
0x18000d8eb  push    rsi
0x18000d8ec  push    rdi
0x18000d8ed  push    r14
0x18000d8ef  push    r15
0x18000d8f1  lea     rbp, [rsp-2Fh]
0x18000d8f6  sub     rsp, 88h
0x18000d8fd  mov     rax, cs:__security_cookie
0x18000d904  xor     rax, rsp
0x18000d907  mov     [rbp+57h+var_40], rax
0x18000d90b  mov     r15, rdx
0x18000d90e  mov     [rbp+57h+var_90], rcx
0x18000d912  mov     rdi, rcx
0x18000d915  mov     rdx, r8
0x18000d918  lea     rcx, [rbp+57h+var_60]
0x18000d91c  mov     rsi, r9
0x18000d91f  mov     r14, r8
0x18000d922  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d927  mov     rdx, rax
0x18000d92a  lea     rcx, [rbp+57h+Src]; Src
0x18000d92e  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18000d933  lea     rcx, [rbp+57h+Src]
0x18000d937  mov     rbx, [rax+10h]
0x18000d93b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d940  lea     rcx, [rbp+57h+Src]
0x18000d944  test    rbx, rbx
0x18000d947  jz      short loc_18000D94E
0x18000d949  mov     rdx, r14
0x18000d94c  jmp     short loc_18000D97E
0x18000d94e  mov     rdx, rsi
0x18000d951  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d956  mov     rdx, rax
0x18000d959  lea     rcx, [rbp+57h+var_60]; Src
0x18000d95d  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18000d962  lea     rcx, [rbp+57h+var_60]
0x18000d966  mov     rbx, [rax+10h]
0x18000d96a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d96f  lea     rcx, [rbp+57h+Src]
0x18000d973  mov     rdx, rsi
0x18000d976  test    rbx, rbx
0x18000d979  jnz     short loc_18000D97E
0x18000d97b  mov     rdx, r15
0x18000d97e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d983  mov     rdx, rax
0x18000d986  mov     rcx, rdi; Src
0x18000d989  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18000d98e  mov     rax, rdi
0x18000d991  mov     rcx, [rbp+57h+var_40]
0x18000d995  xor     rcx, rsp; StackCookie
0x18000d998  call    __security_check_cookie
0x18000d99d  add     rsp, 88h
0x18000d9a4  pop     r15
0x18000d9a6  pop     r14
0x18000d9a8  pop     rdi
0x18000d9a9  pop     rsi
0x18000d9aa  pop     rbx
0x18000d9ab  pop     rbp
0x18000d9ac  retn
```
