# wil::make_unique_cotaskmem<ushort [0]>(unsigned __int64)

- ea: `0x18002f6a4`
- end: `0x18002f740`
- name: `??$make_unique_cotaskmem@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `156`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030a64`

## callees

- `0x18000c0f8`
- `0x18001096c`
- `0x18002f6a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f6d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f6d9`

## string_xrefs

- `0x18002f71c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002f72e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall wil::make_unique_cotaskmem<unsigned short [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  _WORD *v6; // rax
  const char *v7; // r9
  _WORD *v8; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a2 > 0x7FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1802,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v5 = a2;
  v6 = CoTaskMemAlloc(2 * a2);
  *a1 = v6;
  if ( v6 )
  {
    v8 = &v6[v5];
    while ( v6 != v8 )
      *v6++ = 0;
  }
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x1854,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v7);
  return a1;
}

```

## disassembly

```asm
0x18002f6a4  mov     [rsp+arg_8], rbx
0x18002f6a9  mov     [rsp+arg_0], rcx
0x18002f6ae  push    rdi
0x18002f6af  sub     rsp, 30h
0x18002f6b3  mov     rbx, rcx
0x18002f6b6  mov     [rsp+38h+var_18], 0
0x18002f6be  mov     rcx, [rsp+38h]; this
0x18002f6c3  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002f6cd  cmp     rdx, rax
0x18002f6d0  ja      short loc_18002F72E
0x18002f6d2  lea     rdi, [rdx+rdx]
0x18002f6d6  mov     rcx, rdi; cb
0x18002f6d9  call    cs:__imp_CoTaskMemAlloc
0x18002f6df  mov     [rbx], rax
0x18002f6e2  test    rax, rax
0x18002f6e5  jz      short loc_18002F6FB
0x18002f6e7  lea     rcx, [rdi+rax]
0x18002f6eb  jmp     short loc_18002F6F6
0x18002f6ed  xor     edx, edx
0x18002f6ef  mov     [rax], dx
0x18002f6f2  add     rax, 2
0x18002f6f6  cmp     rax, rcx
0x18002f6f9  jnz     short loc_18002F6ED
0x18002f6fb  mov     [rsp+38h+var_18], 1
0x18002f703  mov     rcx, [rsp+38h]; this
0x18002f708  cmp     qword ptr [rbx], 0
0x18002f70c  jz      short loc_18002F71C
0x18002f70e  mov     rax, rbx
0x18002f711  mov     rbx, [rsp+38h+arg_8]
0x18002f716  add     rsp, 30h
0x18002f71a  pop     rdi
0x18002f71b  retn
0x18002f71c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f723  mov     edx, 1854h; void *
0x18002f728  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18002f72e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f735  mov     edx, 1802h; void *
0x18002f73a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
