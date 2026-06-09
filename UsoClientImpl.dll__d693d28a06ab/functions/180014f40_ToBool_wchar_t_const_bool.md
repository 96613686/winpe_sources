# ToBool(wchar_t const *,bool *)

- ea: `0x180014f40`
- end: `0x18001509a`
- name: `?ToBool@@YAJPEB_WPEA_N@Z`
- size: `346`
- prototype: `__int64 __fastcall(const wchar_t *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x180007804`
- `0x180014f40`
- `0x180033f14`
- `0x180036b10`
- `0x18003a204`

## string_xrefs

- `0x180015072`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180015088`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
__int64 __fastcall ToBool(const wchar_t *a1, bool *a2)
{
  bool v2; // bl
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
      (void *)0x537,
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
0x180014f40  mov     [rsp-18h+arg_0], rbx
0x180014f45  mov     [rsp-18h+arg_10], rsi
0x180014f4a  mov     [rsp-18h+arg_18], rdi
0x180014f4f  push    rbp
0x180014f50  push    r14
0x180014f52  push    r15
0x180014f54  mov     rbp, rsp
0x180014f57  sub     rsp, 40h
0x180014f5b  xor     ebx, ebx
0x180014f5d  mov     r14, rdx
0x180014f60  mov     rsi, rcx
0x180014f63  test    rdx, rdx
0x180014f66  jnz     short loc_180014FA1
0x180014f68  mov     rcx, [rbp+18h]; this
0x180014f6c  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x180014f73  mov     r9d, 80070057h; char *
0x180014f79  mov     edx, 537h; void *
0x180014f7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014f83  mov     eax, 80070057h
0x180014f88  mov     rbx, [rsp+40h+arg_0]
0x180014f8d  mov     rsi, [rsp+40h+arg_10]
0x180014f92  mov     rdi, [rsp+40h+arg_18]
0x180014f97  add     rsp, 40h
0x180014f9b  pop     r15
0x180014f9d  pop     r14
0x180014f9f  pop     rbp
0x180014fa0  retn
0x180014fa1  lea     r11, word_180068F6A
0x180014fa8  xor     r8d, r8d
0x180014fab  lea     r15, String2; "TRUE"
0x180014fb2  mov     rdx, r11
0x180014fb5  mov     rcx, r15
0x180014fb8  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180014fbd  cmp     rax, r11
0x180014fc0  jz      loc_180015084
0x180014fc6  sub     rax, r15
0x180014fc9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180014fcd  sar     rax, 1
0x180014fd0  cmp     rax, rdi
0x180014fd3  jz      loc_180015084
0x180014fd9  mov     rcx, rdi
0x180014fdc  inc     rcx
0x180014fdf  cmp     [rsi+rcx*2], bx
0x180014fe3  jnz     short loc_180014FDC
0x180014fe5  mov     [rbp+var_8], rcx
0x180014fe9  lea     rdx, [rbp+var_20]
0x180014fed  lea     rcx, [rbp+var_10]
0x180014ff1  mov     [rbp+var_20], r15
0x180014ff5  mov     [rbp+var_18], rax
0x180014ff9  mov     [rbp+var_10], rsi
0x180014ffd  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180015002  test    al, al
0x180015004  jz      short loc_18001500A
0x180015006  mov     bl, 1
0x180015008  jmp     short loc_180015064
0x18001500a  lea     r11, dword_180068F7C
0x180015011  xor     r8d, r8d
0x180015014  lea     r15, aFalse_1; "FALSE"
0x18001501b  mov     rdx, r11
0x18001501e  mov     rcx, r15
0x180015021  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180015026  cmp     rax, r11
0x180015029  jz      short loc_18001506E
0x18001502b  sub     rax, r15
0x18001502e  sar     rax, 1
0x180015031  cmp     rax, rdi
0x180015034  jz      short loc_18001506E
0x180015036  inc     rdi
0x180015039  cmp     [rsi+rdi*2], bx
0x18001503d  jnz     short loc_180015036
0x18001503f  lea     rdx, [rbp+var_10]
0x180015043  mov     [rbp+var_10], r15
0x180015047  lea     rcx, [rbp+var_20]
0x18001504b  mov     [rbp+var_8], rax
0x18001504f  mov     [rbp+var_20], rsi
0x180015053  mov     [rbp+var_18], rdi
0x180015057  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18001505c  test    al, al
0x18001505e  jz      loc_180014F83
0x180015064  mov     [r14], bl
0x180015067  xor     eax, eax
0x180015069  jmp     loc_180014F88
0x18001506e  mov     rcx, [rbp+18h]; this
0x180015072  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180015079  mov     edx, 0C9h; void *
0x18001507e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180015084  mov     rcx, [rbp+18h]; this
0x180015088  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18001508f  mov     edx, 0C9h; void *
0x180015094  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
