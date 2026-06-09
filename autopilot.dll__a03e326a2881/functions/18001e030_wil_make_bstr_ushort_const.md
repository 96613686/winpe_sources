# wil::make_bstr(ushort const *)

- ea: `0x18001e030`
- end: `0x18001e07e`
- name: `?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d70c`

## callees

- `0x18001e00c`
- `0x18001e030`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001e048`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e048`

## string_xrefs

- `0x18001e06c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18001e030  mov     [rsp+arg_0], rcx
0x18001e035  push    rbx
0x18001e036  sub     rsp, 30h
0x18001e03a  mov     rbx, rcx
0x18001e03d  mov     [rsp+38h+var_18], 0
0x18001e045  mov     rcx, rdx; psz
0x18001e048  call    cs:__imp_SysAllocString
0x18001e04e  mov     [rbx], rax
0x18001e051  mov     [rsp+38h+var_18], 1
0x18001e059  mov     rcx, [rsp+38h]; this
0x18001e05e  test    rax, rax
0x18001e061  jz      short loc_18001E06C
0x18001e063  mov     rax, rbx
0x18001e066  add     rsp, 30h
0x18001e06a  pop     rbx
0x18001e06b  retn
0x18001e06c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e073  mov     edx, 15F3h; void *
0x18001e078  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
