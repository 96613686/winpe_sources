# wil::make_unique_cotaskmem<void * [0]>(unsigned __int64)

- ea: `0x180006f64`
- end: `0x180006fad`
- name: `??$make_unique_cotaskmem@$$BY0A@PEAX@wil@@YA?AV?$unique_ptr@$$BY0A@PEAXU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000314c`

## callees

- `0x180006f64`
- `0x18000701c`
- `0x180009c04`

## string_xrefs

- `0x180006f91`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem<void * [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned int a3,
        const char *a4)
{
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::make_unique_cotaskmem_nothrow<void * [0]>(a1, a2, a3, a4);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x1854,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v5);
  return a1;
}

```

## disassembly

```asm
0x180006f64  mov     [rsp+arg_0], rcx
0x180006f69  push    rbx
0x180006f6a  sub     rsp, 30h
0x180006f6e  mov     rbx, rcx
0x180006f71  mov     [rsp+38h+var_18], 0
0x180006f79  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@PEAX@wil@@YA?AV?$unique_ptr@$$BY0A@PEAXU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<void * [0]>(unsigned __int64)
0x180006f7e  mov     [rsp+38h+var_18], 1
0x180006f86  mov     rcx, [rsp+38h]; this
0x180006f8b  cmp     qword ptr [rbx], 0
0x180006f8f  jnz     short loc_180006FA3
0x180006f91  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006f98  mov     edx, 1854h; void *
0x180006f9d  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180006fa3  mov     rax, rbx
0x180006fa6  add     rsp, 30h
0x180006faa  pop     rbx
0x180006fab  retn
```
