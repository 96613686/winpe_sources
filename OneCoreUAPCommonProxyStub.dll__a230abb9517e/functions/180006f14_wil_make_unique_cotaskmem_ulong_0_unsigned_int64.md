# wil::make_unique_cotaskmem<ulong [0]>(unsigned __int64)

- ea: `0x180006f14`
- end: `0x180006f5d`
- name: `??$make_unique_cotaskmem@$$BY0A@K@wil@@YA?AV?$unique_ptr@$$BY0A@KU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000314c`

## callees

- `0x180006f14`
- `0x180006fb4`
- `0x180009c04`

## string_xrefs

- `0x180006f41`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::make_unique_cotaskmem<unsigned long [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned int a3,
        const char *a4)
{
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::make_unique_cotaskmem_nothrow<unsigned long [0]>(a1, a2, a3, a4);
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
0x180006f14  mov     [rsp+arg_0], rcx
0x180006f19  push    rbx
0x180006f1a  sub     rsp, 30h
0x180006f1e  mov     rbx, rcx
0x180006f21  mov     [rsp+38h+var_18], 0
0x180006f29  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@K@wil@@YA?AV?$unique_ptr@$$BY0A@KU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<ulong [0]>(unsigned __int64)
0x180006f2e  mov     [rsp+38h+var_18], 1
0x180006f36  mov     rcx, [rsp+38h]; this
0x180006f3b  cmp     qword ptr [rbx], 0
0x180006f3f  jnz     short loc_180006F53
0x180006f41  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006f48  mov     edx, 1854h; void *
0x180006f4d  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180006f53  mov     rax, rbx
0x180006f56  add     rsp, 30h
0x180006f5a  pop     rbx
0x180006f5b  retn
```
