# wil::make_unique_hlocal<uchar [0]>(unsigned __int64)

- ea: `0x180004b3c`
- end: `0x180004b85`
- name: `??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `73`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180008e40`
- `0x1800090d0`
- `0x1800092e0`
- `0x180009510`

## callees

- `0x180004b3c`
- `0x180004c7c`
- `0x1800082ac`

## string_xrefs

- `0x180004b69`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall wil::make_unique_hlocal<unsigned char [0]>(_QWORD *a1, __int64 a2)
{
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::make_unique_hlocal_nothrow<unsigned char [0]>(a1, a2);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x1321,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  return a1;
}

```

## disassembly

```asm
0x180004b3c  mov     [rsp+arg_0], rcx
0x180004b41  push    rbx
0x180004b42  sub     rsp, 30h
0x180004b46  mov     rbx, rcx
0x180004b49  mov     [rsp+38h+var_18], 0
0x180004b51  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180004b56  mov     [rsp+38h+var_18], 1
0x180004b5e  mov     rcx, [rsp+38h]; this
0x180004b63  cmp     qword ptr [rbx], 0
0x180004b67  jnz     short loc_180004B7B
0x180004b69  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004b70  mov     edx, 1321h; void *
0x180004b75  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180004b7b  mov     rax, rbx
0x180004b7e  add     rsp, 30h
0x180004b82  pop     rbx
0x180004b83  retn
```
