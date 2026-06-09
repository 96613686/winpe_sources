# wil::make_unique_hlocal<_GUID [0]>(unsigned __int64)

- ea: `0x180004c2c`
- end: `0x180004c75`
- name: `??$make_unique_hlocal@$$BY0A@U_GUID@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `73`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008be0`
- `0x180008ed0`

## callees

- `0x180004c2c`
- `0x180004db0`
- `0x1800082ac`

## string_xrefs

- `0x180004c59`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_hlocal<_GUID [0]>(_QWORD *a1)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::make_unique_hlocal_nothrow<_GUID [0]>(a1);
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
0x180004c2c  mov     [rsp+arg_0], rcx
0x180004c31  push    rbx
0x180004c32  sub     rsp, 30h
0x180004c36  mov     rbx, rcx
0x180004c39  mov     [rsp+38h+var_18], 0
0x180004c41  call    ??$make_unique_hlocal_nothrow@$$BY0A@U_GUID@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<_GUID [0]>(unsigned __int64)
0x180004c46  mov     [rsp+38h+var_18], 1
0x180004c4e  mov     rcx, [rsp+38h]; this
0x180004c53  cmp     qword ptr [rbx], 0
0x180004c57  jnz     short loc_180004C6B
0x180004c59  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004c60  mov     edx, 1321h; void *
0x180004c65  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180004c6b  mov     rax, rbx
0x180004c6e  add     rsp, 30h
0x180004c72  pop     rbx
0x180004c73  retn
```
