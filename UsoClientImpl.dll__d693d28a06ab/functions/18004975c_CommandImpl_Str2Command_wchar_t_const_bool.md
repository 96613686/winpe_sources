# CommandImpl::Str2Command(wchar_t const *,bool)

- ea: `0x18004975c`
- end: `0x1800498a7`
- name: `?Str2Command@CommandImpl@@CA?AW4CommandMode@1@PEB_W_N@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180048d58`

## callees

- `0x180033f14`
- `0x180036b10`
- `0x18003a204`
- `0x18004975c`

## string_xrefs

- `0x18004987f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x180049895`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
__int64 __fastcall CommandImpl::Str2Command(const wchar_t *a1, char a2)
{
  __int64 traits_2_unsigned_short; // rax
  const char *v4; // r9
  __int64 v5; // r11
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  const char *v10; // r9
  __int64 v11; // r11
  __int64 v12; // rax
  const wchar_t *v14; // [rsp+20h] [rbp-20h] BYREF
  __int64 v15; // [rsp+28h] [rbp-18h]
  const wchar_t *v16; // [rsp+30h] [rbp-10h] BYREF
  __int64 v17; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]

  if ( !a2 )
  {
    if ( !a1 || !*a1 )
      return 0;
    traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                L"help",
                                word_18008D35A,
                                0);
    if ( traits_2_unsigned_short == v5 || (v6 = -1, v7 = (traits_2_unsigned_short - (__int64)L"help") >> 1, v7 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v4);
    v8 = -1;
    do
      ++v8;
    while ( a1[v8] );
    v17 = v8;
    v14 = L"help";
    v15 = v7;
    v16 = a1;
    if ( !(unsigned __int8)Strings::iequals(&v16, &v14) )
    {
      v9 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
             L"analyze",
             L"help",
             0);
      if ( v9 == v11 || (v12 = (v9 - (__int64)L"analyze") >> 1, v12 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v10);
      do
        ++v6;
      while ( a1[v6] );
      v16 = L"analyze";
      v17 = v12;
      v14 = a1;
      v15 = v6;
      if ( (unsigned __int8)Strings::iequals(&v14, &v16) )
        return 2;
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18004975c  mov     rax, rsp
0x18004975f  mov     [rax+8], rbx
0x180049763  mov     [rax+10h], rsi
0x180049767  mov     [rax+18h], rdi
0x18004976b  mov     [rax+20h], r14
0x18004976f  push    rbp
0x180049770  mov     rbp, rsp
0x180049773  sub     rsp, 40h
0x180049777  xor     esi, esi
0x180049779  mov     rbx, rcx
0x18004977c  test    dl, dl
0x18004977e  jnz     loc_18004985C
0x180049784  test    rcx, rcx
0x180049787  jz      loc_180049858
0x18004978d  cmp     [rcx], si
0x180049790  jz      loc_180049858
0x180049796  lea     r11, word_18008D35A
0x18004979d  xor     r8d, r8d
0x1800497a0  lea     r14, aHelp; "help"
0x1800497a7  mov     rdx, r11
0x1800497aa  mov     rcx, r14
0x1800497ad  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1800497b2  cmp     rax, r11
0x1800497b5  jz      loc_18004987B
0x1800497bb  sub     rax, r14
0x1800497be  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800497c2  sar     rax, 1
0x1800497c5  cmp     rax, rdi
0x1800497c8  jz      loc_18004987B
0x1800497ce  mov     rcx, rdi
0x1800497d1  inc     rcx
0x1800497d4  cmp     [rbx+rcx*2], si
0x1800497d8  jnz     short loc_1800497D1
0x1800497da  mov     [rbp+var_8], rcx
0x1800497de  lea     rdx, [rbp+var_20]
0x1800497e2  lea     rcx, [rbp+var_10]
0x1800497e6  mov     [rbp+var_20], r14
0x1800497ea  mov     [rbp+var_18], rax
0x1800497ee  mov     [rbp+var_10], rbx
0x1800497f2  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x1800497f7  test    al, al
0x1800497f9  jnz     short loc_18004985C
0x1800497fb  lea     r11, aHelp; "help"
0x180049802  xor     r8d, r8d
0x180049805  lea     r14, aAnalyze; "analyze"
0x18004980c  mov     rdx, r11
0x18004980f  mov     rcx, r14
0x180049812  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180049817  cmp     rax, r11
0x18004981a  jz      short loc_180049891
0x18004981c  sub     rax, r14
0x18004981f  sar     rax, 1
0x180049822  cmp     rax, rdi
0x180049825  jz      short loc_180049891
0x180049827  inc     rdi
0x18004982a  cmp     [rbx+rdi*2], si
0x18004982e  jnz     short loc_180049827
0x180049830  lea     rdx, [rbp+var_10]
0x180049834  mov     [rbp+var_10], r14
0x180049838  lea     rcx, [rbp+var_20]
0x18004983c  mov     [rbp+var_8], rax
0x180049840  mov     [rbp+var_20], rbx
0x180049844  mov     [rbp+var_18], rdi
0x180049848  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18004984d  test    al, al
0x18004984f  jz      short loc_180049858
0x180049851  mov     eax, 2
0x180049856  jmp     short loc_180049861
0x180049858  xor     eax, eax
0x18004985a  jmp     short loc_180049861
0x18004985c  mov     eax, 1
0x180049861  mov     rbx, [rsp+40h+arg_0]
0x180049866  mov     rsi, [rsp+40h+arg_8]
0x18004986b  mov     rdi, [rsp+40h+arg_10]
0x180049870  mov     r14, [rsp+40h+arg_18]
0x180049875  add     rsp, 40h
0x180049879  pop     rbp
0x18004987a  retn
0x18004987b  mov     rcx, [rbp+8]; this
0x18004987f  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180049886  mov     edx, 0C9h; void *
0x18004988b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180049891  mov     rcx, [rbp+8]; this
0x180049895  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18004989c  mov     edx, 0C9h; void *
0x1800498a1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
