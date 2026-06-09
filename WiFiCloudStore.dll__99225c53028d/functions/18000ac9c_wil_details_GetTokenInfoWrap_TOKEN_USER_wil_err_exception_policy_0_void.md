# wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)

- ea: `0x18000ac9c`
- end: `0x18000acec`
- name: `??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `80`
- prototype: `void **__fastcall(void **, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ac14`
- `0x18000b99c`
- `0x180013a94`
- `0x180014d70`

## callees

- `0x18000ac9c`
- `0x18000acf4`
- `0x18002e2d0`

## string_xrefs

- `0x18000acda`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void **__fastcall wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void **a1, __int64 a2)
{
  int token_information; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(a1, a2);
  if ( token_information < 0 )
    wil::details::in1diag3::Throw_Hr(
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
0x18000ac9c  mov     [rsp+arg_0], rcx
0x18000aca1  push    rbx
0x18000aca2  sub     rsp, 30h
0x18000aca6  mov     rbx, rcx
0x18000aca9  mov     [rsp+38h+var_18], 0
0x18000acb1  mov     qword ptr [rcx], 0
0x18000acb8  mov     [rsp+38h+var_18], 1; int
0x18000acc0  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18000acc5  test    eax, eax
0x18000acc7  js      short loc_18000ACD2
0x18000acc9  mov     rax, rbx
0x18000accc  add     rsp, 30h
0x18000acd0  pop     rbx
0x18000acd1  retn
0x18000acd2  mov     rcx, [rsp+38h]; this
0x18000acd7  mov     r9d, eax; char *
0x18000acda  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ace1  mov     edx, 1CBEh; void *
0x18000ace6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
