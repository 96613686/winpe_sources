# wil::make_unique_cotaskmem_nothrow<_SUCCESS_RESULT_HINT [0]>(unsigned __int64)

- ea: `0x18003f6cc`
- end: `0x18003f756`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@U_SUCCESS_RESULT_HINT@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_SUCCESS_RESULT_HINT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `138`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003fb20`

## callees

- `0x18000b2b4`
- `0x180013828`
- `0x18003f6cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f70e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f70e`

## string_xrefs

- `0x18003f6f2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<_SUCCESS_RESULT_HINT [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rsi
  char *v6; // rax
  char *v7; // rbx
  char *v8; // rsi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x141414141414141LL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1802,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v5 = 204 * a2;
  v6 = (char *)CoTaskMemAlloc(204 * a2);
  *a1 = v6;
  v7 = v6;
  if ( v6 )
  {
    v8 = &v6[v5];
    if ( v6 != v8 )
    {
      do
      {
        memset_0(v7, 0, 0xCCu);
        v7 += 204;
      }
      while ( v7 != v8 );
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18003f6cc  mov     [rsp+arg_0], rbx
0x18003f6d1  mov     [rsp+arg_8], rsi
0x18003f6d6  push    rdi
0x18003f6d7  sub     rsp, 20h
0x18003f6db  mov     rax, 141414141414141h
0x18003f6e5  mov     rdi, rcx
0x18003f6e8  cmp     rdx, rax
0x18003f6eb  jbe     short loc_18003F704
0x18003f6ed  mov     rcx, [rsp+28h]; this
0x18003f6f2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f6f9  mov     edx, 1802h; void *
0x18003f6fe  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003f704  imul    rsi, rdx, 0CCh
0x18003f70b  mov     rcx, rsi; cb
0x18003f70e  call    cs:__imp_CoTaskMemAlloc
0x18003f714  mov     [rdi], rax
0x18003f717  mov     rbx, rax
0x18003f71a  test    rax, rax
0x18003f71d  jz      short loc_18003F743
0x18003f71f  add     rsi, rax
0x18003f722  cmp     rax, rsi
0x18003f725  jz      short loc_18003F743
0x18003f727  xor     edx, edx; Val
0x18003f729  mov     r8d, 0CCh; Size
0x18003f72f  mov     rcx, rbx; void *
0x18003f732  call    memset_0
0x18003f737  add     rbx, 0CCh
0x18003f73e  cmp     rbx, rsi
0x18003f741  jnz     short loc_18003F727
0x18003f743  mov     rbx, [rsp+28h+arg_0]
0x18003f748  mov     rax, rdi
0x18003f74b  mov     rsi, [rsp+28h+arg_8]
0x18003f750  add     rsp, 20h
0x18003f754  pop     rdi
0x18003f755  retn
```
