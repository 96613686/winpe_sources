# WindowsMidiServicesInternal::EndpointInterfaceIdContainsString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001b094`
- end: `0x18001b19d`
- name: `?EndpointInterfaceIdContainsString@WindowsMidiServicesInternal@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `265`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001b1b0`

## callees

- `0x1800034e0`
- `0x1800038f0`
- `0x18000bf6c`
- `0x18000d1ac`
- `0x1800116e0`
- `0x18001b094`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall WindowsMidiServicesInternal::EndpointInterfaceIdContainsString(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  unsigned __int16 *v5; // r8
  unsigned __int16 *v6; // rdi
  char *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  bool v10; // bl
  _BYTE v12[32]; // [rsp+28h] [rbp-11h] BYREF
  unsigned __int16 v13[8]; // [rsp+48h] [rbp+Fh] BYREF
  unsigned __int64 v14; // [rsp+58h] [rbp+1Fh]
  unsigned __int64 v15; // [rsp+60h] [rbp+27h]
  unsigned __int16 v16[8]; // [rsp+68h] [rbp+2Fh] BYREF
  unsigned __int64 v17; // [rsp+78h] [rbp+3Fh]
  unsigned __int64 v18; // [rsp+80h] [rbp+47h]

  v3 = std::wstring::wstring(v12, a1);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v16, v3);
  v4 = std::wstring::wstring(v12, a2);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v13, v4);
  if ( v17 && v14 )
  {
    v5 = v13;
    if ( v15 > 7 )
      v5 = *(unsigned __int16 **)v13;
    v6 = v16;
    if ( v18 > 7 )
      v6 = *(unsigned __int16 **)v16;
    if ( v14 > v17 || (v7 = (char *)&v6[v17], v8 = _std_search_2(v6, v7, v5), (char *)v8 == v7) )
      v9 = -1;
    else
      v9 = (v8 - (__int64)v6) >> 1;
    v10 = v9 != -1;
    std::wstring::~wstring(v13);
    std::wstring::~wstring(v16);
    return v10;
  }
  else
  {
    std::wstring::~wstring(v13);
    std::wstring::~wstring(v16);
    return 0;
  }
}

```

## disassembly

```asm
0x18001b094  mov     [rsp-8+arg_10], rbx
0x18001b099  mov     [rsp-8+arg_18], rdi
0x18001b09e  push    rbp
0x18001b09f  lea     rbp, [rsp-57h]
0x18001b0a4  sub     rsp, 90h
0x18001b0ab  mov     rax, cs:__security_cookie
0x18001b0b2  xor     rax, rsp
0x18001b0b5  mov     [rbp+57h+var_8], rax
0x18001b0b9  mov     rbx, rdx
0x18001b0bc  mov     rdx, rcx
0x18001b0bf  lea     rcx, [rbp+57h+var_68]
0x18001b0c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b0c8  mov     rdx, rax
0x18001b0cb  lea     rcx, [rbp+57h+var_28]
0x18001b0cf  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x18001b0d4  nop
0x18001b0d5  mov     rdx, rbx
0x18001b0d8  lea     rcx, [rbp+57h+var_68]
0x18001b0dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b0e1  mov     rdx, rax
0x18001b0e4  lea     rcx, [rbp+57h+var_48]
0x18001b0e8  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x18001b0ed  mov     rax, [rbp+57h+var_18]
0x18001b0f1  test    rax, rax
0x18001b0f4  jz      short loc_18001B167
0x18001b0f6  mov     r9, [rbp+57h+var_38]
0x18001b0fa  test    r9, r9
0x18001b0fd  jz      short loc_18001B167
0x18001b0ff  lea     r8, [rbp+57h+var_48]
0x18001b103  cmp     [rbp+57h+var_30], 7
0x18001b108  cmova   r8, qword ptr [rbp+57h+var_48]
0x18001b10d  lea     rdi, [rbp+57h+var_28]
0x18001b111  cmp     [rbp+57h+var_10], 7
0x18001b116  cmova   rdi, qword ptr [rbp+57h+var_28]
0x18001b11b  cmp     r9, rax
0x18001b11e  ja      short loc_18001B145
0x18001b120  test    r9, r9
0x18001b123  jnz     short loc_18001B129
0x18001b125  xor     eax, eax
0x18001b127  jmp     short loc_18001B149
0x18001b129  lea     rbx, [rdi+rax*2]
0x18001b12d  mov     rdx, rbx
0x18001b130  mov     rcx, rdi
0x18001b133  call    __std_search_2
0x18001b138  cmp     rax, rbx
0x18001b13b  jz      short loc_18001B145
0x18001b13d  sub     rax, rdi
0x18001b140  sar     rax, 1
0x18001b143  jmp     short loc_18001B149
0x18001b145  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b149  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b14d  setnz   bl
0x18001b150  lea     rcx, [rbp+57h+var_48]
0x18001b154  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b159  nop
0x18001b15a  lea     rcx, [rbp+57h+var_28]
0x18001b15e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b163  mov     al, bl
0x18001b165  jmp     short loc_18001B17C
0x18001b167  lea     rcx, [rbp+57h+var_48]
0x18001b16b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b170  nop
0x18001b171  lea     rcx, [rbp+57h+var_28]
0x18001b175  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b17a  xor     al, al
0x18001b17c  mov     rcx, [rbp+57h+var_8]
0x18001b180  xor     rcx, rsp; StackCookie
0x18001b183  call    __security_check_cookie
0x18001b188  lea     r11, [rsp+90h+var_s0]
0x18001b190  mov     rbx, [r11+20h]
0x18001b194  mov     rdi, [r11+28h]
0x18001b198  mov     rsp, r11
0x18001b19b  pop     rbp
0x18001b19c  retn
```
