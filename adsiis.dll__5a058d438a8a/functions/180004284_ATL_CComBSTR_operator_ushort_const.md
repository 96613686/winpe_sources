# ATL::CComBSTR::operator=(ushort const *)

- ea: `0x180004284`
- end: `0x1800042b7`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z`
- size: `51`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180004624`
- `0x1800049c0`
- `0x18001c398`
- `0x18001c4b8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800042a0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800042a0`
- `OLEAUT32!__imp_SysFreeString` at `0x180004297`
- `OLEAUT32!__imp_SysFreeString` at `0x180004297`

## pseudocode

```c
BSTR *__fastcall ATL::CComBSTR::operator=(BSTR *a1, const OLECHAR *a2)
{
  SysFreeString(*a1);
  *a1 = SysAllocString(a2);
  return a1;
}

```

## disassembly

```asm
0x180004284  mov     [rsp+arg_0], rbx
0x180004289  push    rdi
0x18000428a  sub     rsp, 20h
0x18000428e  mov     rdi, rcx
0x180004291  mov     rbx, rdx
0x180004294  mov     rcx, [rcx]; bstrString
0x180004297  call    cs:__imp_SysFreeString
0x18000429d  mov     rcx, rbx; psz
0x1800042a0  call    cs:__imp_SysAllocString
0x1800042a6  mov     rbx, [rsp+28h+arg_0]
0x1800042ab  mov     [rdi], rax
0x1800042ae  mov     rax, rdi
0x1800042b1  add     rsp, 20h
0x1800042b5  pop     rdi
0x1800042b6  retn
```
