# wil::make_unique_hlocal<ushort [0]>(unsigned __int64)

- ea: `0x180004b8c`
- end: `0x180004bd5`
- name: `??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `73`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008cc0`
- `0x180009160`
- `0x180009610`

## callees

- `0x180004b8c`
- `0x180004cc4`
- `0x1800082ac`

## string_xrefs

- `0x180004bb9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall wil::make_unique_hlocal<unsigned short [0]>(_QWORD *a1)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::make_unique_hlocal_nothrow<unsigned short [0]>(a1);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x1321,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
  return a1;
}

```

## disassembly

```asm
0x180004b8c  mov     [rsp+arg_0], rcx
0x180004b91  push    rbx
0x180004b92  sub     rsp, 30h
0x180004b96  mov     rbx, rcx
0x180004b99  mov     [rsp+38h+var_18], 0
0x180004ba1  call    ??$make_unique_hlocal_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<ushort [0]>(unsigned __int64)
0x180004ba6  mov     [rsp+38h+var_18], 1
0x180004bae  mov     rcx, [rsp+38h]; this
0x180004bb3  cmp     qword ptr [rbx], 0
0x180004bb7  jnz     short loc_180004BCB
0x180004bb9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004bc0  mov     edx, 1321h; void *
0x180004bc5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180004bcb  mov     rax, rbx
0x180004bce  add     rsp, 30h
0x180004bd2  pop     rbx
0x180004bd3  retn
```
