# wil::make_bstr(ushort const *)

- ea: `0x1800285e8`
- end: `0x18002862f`
- name: `?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z`
- size: `71`
- prototype: `BSTR *__fastcall(BSTR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180028110`

## callees

- `0x1800285cc`
- `0x1800285e8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180028604`
- `OLEAUT32!__imp_SysAllocString` at `0x180028604`

## string_xrefs

- `0x1800285fd`: `IsInstalled=0 and Type='Software' and IsHidden=0 and IsAssigned=1 and CategoryIDs contains 'e6cf1350-c01b-414d-a61f-263d14d133b4'`

## pseudocode

```c
BSTR *__fastcall wil::make_bstr(BSTR *a1)
{
  BSTR v2; // rax
  void *v3; // rdx
  unsigned int v4; // r8d
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = SysAllocString(
         L"IsInstalled=0 and Type='Software' and IsHidden=0 and IsAssigned=1 and CategoryIDs contains 'e6cf1350-c01b-414d-"
          "a61f-263d14d133b4'");
  *a1 = v2;
  if ( !v2 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v3, v4, v5);
  return a1;
}

```

## disassembly

```asm
0x1800285e8  mov     [rsp+arg_0], rcx
0x1800285ed  push    rbx
0x1800285ee  sub     rsp, 30h
0x1800285f2  mov     rbx, rcx
0x1800285f5  mov     [rsp+38h+var_18], 0
0x1800285fd  lea     rcx, aIsinstalled0An; "IsInstalled=0 and Type='Software' and I"...
0x180028604  call    cs:__imp_SysAllocString
0x18002860a  mov     [rbx], rax
0x18002860d  mov     [rsp+38h+var_18], 1
0x180028615  mov     rcx, [rsp+38h]; this
0x18002861a  test    rax, rax
0x18002861d  jnz     short loc_180028625
0x18002861f  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180028625  mov     rax, rbx
0x180028628  add     rsp, 30h
0x18002862c  pop     rbx
0x18002862d  retn
```
