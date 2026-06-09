# wil::make_bstr(ushort const *)

- ea: `0x1800222e4`
- end: `0x180022332`
- name: `?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z`
- size: `78`
- prototype: `BSTR *__fastcall(BSTR *, const OLECHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b970`
- `0x18001cb18`

## callees

- `0x180021470`
- `0x1800222e4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800222fc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800222fc`

## string_xrefs

- `0x180022320`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
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
0x1800222e4  mov     [rsp+arg_0], rcx
0x1800222e9  push    rbx
0x1800222ea  sub     rsp, 30h
0x1800222ee  mov     rbx, rcx
0x1800222f1  mov     [rsp+38h+var_18], 0
0x1800222f9  mov     rcx, rdx; psz
0x1800222fc  call    cs:__imp_SysAllocString
0x180022302  mov     [rbx], rax
0x180022305  mov     [rsp+38h+var_18], 1
0x18002230d  mov     rcx, [rsp+38h]; this
0x180022312  test    rax, rax
0x180022315  jz      short loc_180022320
0x180022317  mov     rax, rbx
0x18002231a  add     rsp, 30h
0x18002231e  pop     rbx
0x18002231f  retn
0x180022320  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180022327  mov     edx, 15F3h; void *
0x18002232c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
