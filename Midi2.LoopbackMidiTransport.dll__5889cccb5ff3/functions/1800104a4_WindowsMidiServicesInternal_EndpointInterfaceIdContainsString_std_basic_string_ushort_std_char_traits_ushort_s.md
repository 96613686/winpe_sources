# WindowsMidiServicesInternal::EndpointInterfaceIdContainsString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800104a4`
- end: `0x1800105ad`
- name: `?EndpointInterfaceIdContainsString@WindowsMidiServicesInternal@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `265`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180011980`

## callees

- `0x180003d70`
- `0x180004180`
- `0x18000b740`
- `0x18000f0a4`
- `0x1800104a4`
- `0x180013294`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall WindowsMidiServicesInternal::EndpointInterfaceIdContainsString(__int64 a1, __int64 a2)
{
  void *v3; // rax
  void *v4; // rax
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

  v3 = (void *)std::wstring::wstring(v12, a1);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v16, v3);
  v4 = (void *)std::wstring::wstring(v12, a2);
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
0x1800104a4  mov     [rsp-8+arg_10], rbx
0x1800104a9  mov     [rsp-8+arg_18], rdi
0x1800104ae  push    rbp
0x1800104af  lea     rbp, [rsp-57h]
0x1800104b4  sub     rsp, 90h
0x1800104bb  mov     rax, cs:__security_cookie
0x1800104c2  xor     rax, rsp
0x1800104c5  mov     [rbp+57h+var_8], rax
0x1800104c9  mov     rbx, rdx
0x1800104cc  mov     rdx, rcx
0x1800104cf  lea     rcx, [rbp+57h+var_68]
0x1800104d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800104d8  mov     rdx, rax
0x1800104db  lea     rcx, [rbp+57h+var_28]
0x1800104df  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x1800104e4  nop
0x1800104e5  mov     rdx, rbx
0x1800104e8  lea     rcx, [rbp+57h+var_68]
0x1800104ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800104f1  mov     rdx, rax
0x1800104f4  lea     rcx, [rbp+57h+var_48]
0x1800104f8  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x1800104fd  mov     rax, [rbp+57h+var_18]
0x180010501  test    rax, rax
0x180010504  jz      short loc_180010577
0x180010506  mov     r9, [rbp+57h+var_38]
0x18001050a  test    r9, r9
0x18001050d  jz      short loc_180010577
0x18001050f  lea     r8, [rbp+57h+var_48]
0x180010513  cmp     [rbp+57h+var_30], 7
0x180010518  cmova   r8, qword ptr [rbp+57h+var_48]
0x18001051d  lea     rdi, [rbp+57h+var_28]
0x180010521  cmp     [rbp+57h+var_10], 7
0x180010526  cmova   rdi, qword ptr [rbp+57h+var_28]
0x18001052b  cmp     r9, rax
0x18001052e  ja      short loc_180010555
0x180010530  test    r9, r9
0x180010533  jnz     short loc_180010539
0x180010535  xor     eax, eax
0x180010537  jmp     short loc_180010559
0x180010539  lea     rbx, [rdi+rax*2]
0x18001053d  mov     rdx, rbx
0x180010540  mov     rcx, rdi
0x180010543  call    __std_search_2
0x180010548  cmp     rax, rbx
0x18001054b  jz      short loc_180010555
0x18001054d  sub     rax, rdi
0x180010550  sar     rax, 1
0x180010553  jmp     short loc_180010559
0x180010555  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010559  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001055d  setnz   bl
0x180010560  lea     rcx, [rbp+57h+var_48]; void *
0x180010564  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010569  nop
0x18001056a  lea     rcx, [rbp+57h+var_28]; void *
0x18001056e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010573  mov     al, bl
0x180010575  jmp     short loc_18001058C
0x180010577  lea     rcx, [rbp+57h+var_48]; void *
0x18001057b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010580  nop
0x180010581  lea     rcx, [rbp+57h+var_28]; void *
0x180010585  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001058a  xor     al, al
0x18001058c  mov     rcx, [rbp+57h+var_8]
0x180010590  xor     rcx, rsp; StackCookie
0x180010593  call    __security_check_cookie
0x180010598  lea     r11, [rsp+90h+var_s0]
0x1800105a0  mov     rbx, [r11+20h]
0x1800105a4  mov     rdi, [r11+28h]
0x1800105a8  mov     rsp, r11
0x1800105ab  pop     rbp
0x1800105ac  retn
```
