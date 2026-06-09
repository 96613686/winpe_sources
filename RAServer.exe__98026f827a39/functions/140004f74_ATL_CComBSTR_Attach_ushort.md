# ATL::CComBSTR::Attach(ushort *)

- ea: `0x140004f74`
- end: `0x140004fa0`
- name: `?Attach@CComBSTR@ATL@@QEAAXPEAG@Z`
- size: `44`
- prototype: `void __fastcall(BSTR *this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400076a0`
- `0x140013c10`

## callees

- `0x140004f74`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140004f8c`
- `OLEAUT32!__imp_SysFreeString` at `0x140004f8c`

## pseudocode

```c
void __fastcall ATL::CComBSTR::Attach(BSTR *this, unsigned __int16 *a2)
{
  if ( *this != a2 )
  {
    SysFreeString(*this);
    *this = a2;
  }
}

```

## disassembly

```asm
0x140004f74  mov     [rsp+arg_0], rbx
0x140004f79  push    rdi
0x140004f7a  sub     rsp, 20h
0x140004f7e  mov     rbx, rdx
0x140004f81  mov     rdi, rcx
0x140004f84  cmp     [rcx], rdx
0x140004f87  jz      short loc_140004F95
0x140004f89  mov     rcx, [rcx]; bstrString
0x140004f8c  call    cs:__imp_SysFreeString
0x140004f92  mov     [rdi], rbx
0x140004f95  mov     rbx, [rsp+28h+arg_0]
0x140004f9a  add     rsp, 20h
0x140004f9e  pop     rdi
0x140004f9f  retn
```
