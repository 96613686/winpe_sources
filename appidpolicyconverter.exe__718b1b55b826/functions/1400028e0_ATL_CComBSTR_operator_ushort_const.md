# ATL::CComBSTR::operator=(ushort const *)

- ea: `0x1400028e0`
- end: `0x14000292f`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z`
- size: `79`
- prototype: `BSTR *__fastcall(BSTR *, const OLECHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000414c`

## callees

- `0x1400028e0`
- `0x140002b90`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140002906`
- `OLEAUT32!__imp_SysAllocString` at `0x140002906`
- `OLEAUT32!__imp_SysFreeString` at `0x1400028f8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400028f8`

## pseudocode

```c
BSTR *__fastcall ATL::CComBSTR::operator=(BSTR *a1, const OLECHAR *a2)
{
  BSTR v4; // rax
  int v5; // ecx

  if ( a2 != *a1 )
  {
    SysFreeString(*a1);
    if ( a2 )
    {
      v4 = SysAllocString(a2);
      *a1 = v4;
      if ( !v4 )
        ATL::AtlThrowImpl(v5);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1400028e0  mov     [rsp+arg_0], rbx
0x1400028e5  push    rdi
0x1400028e6  sub     rsp, 20h
0x1400028ea  mov     rdi, rdx
0x1400028ed  mov     rbx, rcx
0x1400028f0  cmp     rdx, [rcx]
0x1400028f3  jz      short loc_140002921
0x1400028f5  mov     rcx, [rcx]; bstrString
0x1400028f8  call    cs:__imp_SysFreeString
0x1400028fe  test    rdi, rdi
0x140002901  jz      short loc_14000291A
0x140002903  mov     rcx, rdi; psz
0x140002906  call    cs:__imp_SysAllocString
0x14000290c  mov     [rbx], rax
0x14000290f  test    rax, rax
0x140002912  jnz     short loc_140002921
0x140002914  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000291a  mov     qword ptr [rbx], 0
0x140002921  mov     rax, rbx
0x140002924  mov     rbx, [rsp+28h+arg_0]
0x140002929  add     rsp, 20h
0x14000292d  pop     rdi
0x14000292e  retn
```
