# wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)

- ea: `0x18002c8cc`
- end: `0x18002c91c`
- name: `??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002d454`

## callees

- `0x18000cf94`
- `0x18002c8cc`
- `0x18002cb68`

## string_xrefs

- `0x18002c90a`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void **a1, __int64 a2)
{
  int token_information; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(a1, a2);
  if ( token_information < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)token_information,
      1);
  return a1;
}

```

## disassembly

```asm
0x18002c8cc  mov     [rsp+arg_0], rcx
0x18002c8d1  push    rbx
0x18002c8d2  sub     rsp, 30h
0x18002c8d6  mov     rbx, rcx
0x18002c8d9  mov     [rsp+38h+var_18], 0
0x18002c8e1  mov     qword ptr [rcx], 0
0x18002c8e8  mov     [rsp+38h+var_18], 1; int
0x18002c8f0  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18002c8f5  test    eax, eax
0x18002c8f7  js      short loc_18002C902
0x18002c8f9  mov     rax, rbx
0x18002c8fc  add     rsp, 30h
0x18002c900  pop     rbx
0x18002c901  retn
0x18002c902  mov     rcx, [rsp+38h]; this
0x18002c907  mov     r9d, eax; char *
0x18002c90a  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c911  mov     edx, 1CBEh; void *
0x18002c916  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
