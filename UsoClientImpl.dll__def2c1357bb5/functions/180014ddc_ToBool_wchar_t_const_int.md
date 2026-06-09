# ToBool(wchar_t const *,int *)

- ea: `0x180014ddc`
- end: `0x180014f39`
- name: `?ToBool@@YAJPEB_WPEAH@Z`
- size: `349`
- prototype: `__int64 __fastcall(const wchar_t *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x180007804`
- `0x180014ddc`
- `0x180033f14`
- `0x180036b10`
- `0x18003a204`

## string_xrefs

- `0x180014f11`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180014f27`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
__int64 __fastcall ToBool(const wchar_t *a1, int *a2)
{
  int v2; // ebx
  __int64 traits_2_unsigned_short; // rax
  const char *v7; // r9
  __int64 v8; // r11
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  const char *v13; // r9
  __int64 v14; // r11
  __int64 v15; // rax
  const wchar_t *v16; // [rsp+20h] [rbp-20h] BYREF
  __int64 v17; // [rsp+28h] [rbp-18h]
  const wchar_t *v18; // [rsp+30h] [rbp-10h] BYREF
  __int64 v19; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]

  v2 = 0;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x523,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      (const char *)0x80070057LL,
      (int)v16);
    return 2147942487LL;
  }
  traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                              L"TRUE",
                              word_180068F6A,
                              0);
  if ( traits_2_unsigned_short == v8 || (v9 = -1, v10 = (traits_2_unsigned_short - (__int64)L"TRUE") >> 1, v10 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v7);
  v11 = -1;
  do
    ++v11;
  while ( a1[v11] );
  v19 = v11;
  v16 = L"TRUE";
  v17 = v10;
  v18 = a1;
  if ( (unsigned __int8)Strings::iequals(&v18, &v16) )
  {
    v2 = 1;
  }
  else
  {
    v12 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"FALSE",
            &dword_180068F7C,
            0);
    if ( v12 == v14 || (v15 = (v12 - (__int64)L"FALSE") >> 1, v15 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v13);
    do
      ++v9;
    while ( a1[v9] );
    v18 = L"FALSE";
    v19 = v15;
    v16 = a1;
    v17 = v9;
    if ( !(unsigned __int8)Strings::iequals(&v16, &v18) )
      return 2147942487LL;
  }
  *a2 = v2;
  return 0;
}

```

## disassembly

```asm
0x180014ddc  mov     [rsp-18h+arg_0], rbx
0x180014de1  mov     [rsp-18h+arg_10], rsi
0x180014de6  mov     [rsp-18h+arg_18], rdi
0x180014deb  push    rbp
0x180014dec  push    r14
0x180014dee  push    r15
0x180014df0  mov     rbp, rsp
0x180014df3  sub     rsp, 40h
0x180014df7  xor     ebx, ebx
0x180014df9  mov     r14, rdx
0x180014dfc  mov     rsi, rcx
0x180014dff  test    rdx, rdx
0x180014e02  jnz     short loc_180014E3D
0x180014e04  mov     rcx, [rbp+18h]; this
0x180014e08  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x180014e0f  mov     r9d, 80070057h; char *
0x180014e15  mov     edx, 523h; void *
0x180014e1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014e1f  mov     eax, 80070057h
0x180014e24  mov     rbx, [rsp+40h+arg_0]
0x180014e29  mov     rsi, [rsp+40h+arg_10]
0x180014e2e  mov     rdi, [rsp+40h+arg_18]
0x180014e33  add     rsp, 40h
0x180014e37  pop     r15
0x180014e39  pop     r14
0x180014e3b  pop     rbp
0x180014e3c  retn
0x180014e3d  lea     r11, word_180068F6A
0x180014e44  xor     r8d, r8d
0x180014e47  lea     r15, String2; "TRUE"
0x180014e4e  mov     rdx, r11
0x180014e51  mov     rcx, r15
0x180014e54  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180014e59  cmp     rax, r11
0x180014e5c  jz      loc_180014F23
0x180014e62  sub     rax, r15
0x180014e65  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180014e69  sar     rax, 1
0x180014e6c  cmp     rax, rdi
0x180014e6f  jz      loc_180014F23
0x180014e75  mov     rcx, rdi
0x180014e78  inc     rcx
0x180014e7b  cmp     [rsi+rcx*2], bx
0x180014e7f  jnz     short loc_180014E78
0x180014e81  mov     [rbp+var_8], rcx
0x180014e85  lea     rdx, [rbp+var_20]
0x180014e89  lea     rcx, [rbp+var_10]
0x180014e8d  mov     [rbp+var_20], r15
0x180014e91  mov     [rbp+var_18], rax
0x180014e95  mov     [rbp+var_10], rsi
0x180014e99  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180014e9e  test    al, al
0x180014ea0  jz      short loc_180014EA9
0x180014ea2  mov     ebx, 1
0x180014ea7  jmp     short loc_180014F03
0x180014ea9  lea     r11, dword_180068F7C
0x180014eb0  xor     r8d, r8d
0x180014eb3  lea     r15, aFalse_1; "FALSE"
0x180014eba  mov     rdx, r11
0x180014ebd  mov     rcx, r15
0x180014ec0  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180014ec5  cmp     rax, r11
0x180014ec8  jz      short loc_180014F0D
0x180014eca  sub     rax, r15
0x180014ecd  sar     rax, 1
0x180014ed0  cmp     rax, rdi
0x180014ed3  jz      short loc_180014F0D
0x180014ed5  inc     rdi
0x180014ed8  cmp     [rsi+rdi*2], bx
0x180014edc  jnz     short loc_180014ED5
0x180014ede  lea     rdx, [rbp+var_10]
0x180014ee2  mov     [rbp+var_10], r15
0x180014ee6  lea     rcx, [rbp+var_20]
0x180014eea  mov     [rbp+var_8], rax
0x180014eee  mov     [rbp+var_20], rsi
0x180014ef2  mov     [rbp+var_18], rdi
0x180014ef6  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180014efb  test    al, al
0x180014efd  jz      loc_180014E1F
0x180014f03  mov     [r14], ebx
0x180014f06  xor     eax, eax
0x180014f08  jmp     loc_180014E24
0x180014f0d  mov     rcx, [rbp+18h]; this
0x180014f11  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180014f18  mov     edx, 0C9h; void *
0x180014f1d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180014f23  mov     rcx, [rbp+18h]; this
0x180014f27  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180014f2e  mov     edx, 0C9h; void *
0x180014f33  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
