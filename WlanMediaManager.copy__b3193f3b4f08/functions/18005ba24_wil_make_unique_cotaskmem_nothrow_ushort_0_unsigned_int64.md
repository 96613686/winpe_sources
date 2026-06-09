# wil::make_unique_cotaskmem_nothrow<ushort [0]>(unsigned __int64)

- ea: `0x18005ba24`
- end: `0x18005ba8e`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005b9d4`

## callees

- `0x1800081e8`
- `0x18005ba24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ba5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ba5e`

## string_xrefs

- `0x18005ba45`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<unsigned short [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  _WORD *v6; // rax
  _WORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

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
    v7 = &v6[v5];
    while ( v6 != v7 )
      *v6++ = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18005ba24  mov     [rsp+arg_0], rbx
0x18005ba29  push    rdi
0x18005ba2a  sub     rsp, 20h
0x18005ba2e  mov     rax, 7FFFFFFFFFFFFFFFh
0x18005ba38  mov     rbx, rcx
0x18005ba3b  cmp     rdx, rax
0x18005ba3e  jbe     short loc_18005BA57
0x18005ba40  mov     rcx, [rsp+28h]; this
0x18005ba45  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005ba4c  mov     edx, 1802h; void *
0x18005ba51  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005ba57  lea     rdi, [rdx+rdx]
0x18005ba5b  mov     rcx, rdi; cb
0x18005ba5e  call    cs:__imp_CoTaskMemAlloc
0x18005ba64  mov     [rbx], rax
0x18005ba67  test    rax, rax
0x18005ba6a  jz      short loc_18005BA80
0x18005ba6c  lea     rcx, [rdi+rax]
0x18005ba70  jmp     short loc_18005BA7B
0x18005ba72  xor     edx, edx
0x18005ba74  mov     [rax], dx
0x18005ba77  add     rax, 2
0x18005ba7b  cmp     rax, rcx
0x18005ba7e  jnz     short loc_18005BA72
0x18005ba80  mov     rax, rbx
0x18005ba83  mov     rbx, [rsp+28h+arg_0]
0x18005ba88  add     rsp, 20h
0x18005ba8c  pop     rdi
0x18005ba8d  retn
```
