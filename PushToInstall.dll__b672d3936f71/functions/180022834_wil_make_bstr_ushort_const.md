# wil::make_bstr(ushort const *)

- ea: `0x180022834`
- end: `0x180022882`
- name: `?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022408`

## callees

- `0x180022810`
- `0x180022834`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002284c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002284c`

## string_xrefs

- `0x180022870`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BSTR *__fastcall wil::make_bstr(BSTR *a1, const OLECHAR *a2)
{
  BSTR v3; // rax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = SysAllocString(a2);
  *a1 = v3;
  if ( !v3 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v4);
  return a1;
}

```

## disassembly

```asm
0x180022834  mov     [rsp+arg_0], rcx
0x180022839  push    rbx
0x18002283a  sub     rsp, 30h
0x18002283e  mov     rbx, rcx
0x180022841  mov     [rsp+38h+var_18], 0
0x180022849  mov     rcx, rdx; psz
0x18002284c  call    cs:__imp_SysAllocString
0x180022852  mov     [rbx], rax
0x180022855  mov     [rsp+38h+var_18], 1
0x18002285d  mov     rcx, [rsp+38h]; this
0x180022862  test    rax, rax
0x180022865  jz      short loc_180022870
0x180022867  mov     rax, rbx
0x18002286a  add     rsp, 30h
0x18002286e  pop     rbx
0x18002286f  retn
0x180022870  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180022877  mov     edx, 15F3h; void *
0x18002287c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
