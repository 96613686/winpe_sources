# wil::make_unique_cotaskmem<int,>(void)

- ea: `0x180047b94`
- end: `0x180047bf5`
- name: `??$make_unique_cotaskmem@H$$V@wil@@YA?AV?$unique_ptr@HU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ`
- size: `97`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800112d0`

## callees

- `0x180023814`
- `0x180047b94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047bae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047bae`

## string_xrefs

- `0x180047bd9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem<int,>(_QWORD *a1)
{
  _DWORD *v2; // rax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = CoTaskMemAlloc(4u);
  *a1 = v2;
  if ( v2 )
    *v2 = 0;
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x1841,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  return a1;
}

```

## disassembly

```asm
0x180047b94  mov     [rsp+arg_0], rcx
0x180047b99  push    rbx
0x180047b9a  sub     rsp, 30h
0x180047b9e  mov     rbx, rcx
0x180047ba1  mov     [rsp+38h+var_18], 0
0x180047ba9  mov     ecx, 4; cb
0x180047bae  call    cs:__imp_CoTaskMemAlloc
0x180047bb5  nop     dword ptr [rax+rax+00h]
0x180047bba  mov     [rbx], rax
0x180047bbd  test    rax, rax
0x180047bc0  jz      short loc_180047BC6
0x180047bc2  xor     ecx, ecx
0x180047bc4  mov     [rax], ecx
0x180047bc6  mov     [rsp+38h+var_18], 1
0x180047bce  mov     rcx, [rsp+38h]; this
0x180047bd3  cmp     qword ptr [rbx], 0
0x180047bd7  jnz     short loc_180047BEB
0x180047bd9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180047be0  mov     edx, 1841h; void *
0x180047be5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180047beb  mov     rax, rbx
0x180047bee  add     rsp, 30h
0x180047bf2  pop     rbx
0x180047bf3  retn
```
