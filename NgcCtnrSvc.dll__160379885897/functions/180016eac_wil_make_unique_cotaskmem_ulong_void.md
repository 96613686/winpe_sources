# wil::make_unique_cotaskmem<ulong,>(void)

- ea: `0x180016eac`
- end: `0x180016f0d`
- name: `??$make_unique_cotaskmem@K$$V@wil@@YA?AV?$unique_ptr@KU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ`
- size: `97`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cd38`
- `0x1800112d0`

## callees

- `0x180016eac`
- `0x180023814`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016ec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016ec6`

## string_xrefs

- `0x180016ef1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall wil::make_unique_cotaskmem<unsigned long,>(_QWORD *a1)
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
0x180016eac  mov     [rsp+arg_0], rcx
0x180016eb1  push    rbx
0x180016eb2  sub     rsp, 30h
0x180016eb6  mov     rbx, rcx
0x180016eb9  mov     [rsp+38h+var_18], 0
0x180016ec1  mov     ecx, 4; cb
0x180016ec6  call    cs:__imp_CoTaskMemAlloc
0x180016ecd  nop     dword ptr [rax+rax+00h]
0x180016ed2  mov     [rbx], rax
0x180016ed5  test    rax, rax
0x180016ed8  jz      short loc_180016EDE
0x180016eda  xor     ecx, ecx
0x180016edc  mov     [rax], ecx
0x180016ede  mov     [rsp+38h+var_18], 1
0x180016ee6  mov     rcx, [rsp+38h]; this
0x180016eeb  cmp     qword ptr [rbx], 0
0x180016eef  jnz     short loc_180016F03
0x180016ef1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016ef8  mov     edx, 1841h; void *
0x180016efd  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180016f03  mov     rax, rbx
0x180016f06  add     rsp, 30h
0x180016f0a  pop     rbx
0x180016f0b  retn
```
