# wil::make_bstr(ushort const *)

- ea: `0x18001e860`
- end: `0x18001e8b5`
- name: `?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z`
- size: `85`
- prototype: `BSTR *__fastcall(BSTR *, const OLECHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001dea4`

## callees

- `0x18001e83c`
- `0x18001e860`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001e878`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e878`

## string_xrefs

- `0x18001e8a3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18001e860  mov     [rsp+arg_0], rcx
0x18001e865  push    rbx
0x18001e866  sub     rsp, 30h
0x18001e86a  mov     rbx, rcx
0x18001e86d  mov     [rsp+38h+var_18], 0
0x18001e875  mov     rcx, rdx; psz
0x18001e878  call    cs:__imp_SysAllocString
0x18001e87f  nop     dword ptr [rax+rax+00h]
0x18001e884  mov     [rbx], rax
0x18001e887  mov     [rsp+38h+var_18], 1
0x18001e88f  mov     rcx, [rsp+38h]; this
0x18001e894  test    rax, rax
0x18001e897  jz      short loc_18001E8A3
0x18001e899  mov     rax, rbx
0x18001e89c  add     rsp, 30h
0x18001e8a0  pop     rbx
0x18001e8a1  retn
0x18001e8a3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e8aa  mov     edx, 15F3h; void *
0x18001e8af  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
