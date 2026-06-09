# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x14000e664`
- end: `0x14000e69a`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `54`
- prototype: `ATL::CComBSTR *__fastcall(ATL::CComBSTR *this, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000efc0`
- `0x140011bd8`
- `0x140011d10`
- `0x140011fc0`
- `0x140012fe0`
- `0x140013250`
- `0x140014894`

## callees

- `0x140004f54`
- `0x14000e664`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000e681`
- `OLEAUT32!__imp_SysAllocString` at `0x14000e681`

## pseudocode

```c
ATL::CComBSTR *__fastcall ATL::CComBSTR::CComBSTR(ATL::CComBSTR *this, const unsigned __int16 *a2)
{
  BSTR v4; // rax

  if ( a2 )
  {
    v4 = SysAllocString(a2);
    *(_QWORD *)this = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    *(_QWORD *)this = 0;
  }
  return this;
}

```

## disassembly

```asm
0x14000e664  push    rbx
0x14000e666  sub     rsp, 20h
0x14000e66a  mov     rbx, rcx
0x14000e66d  test    rdx, rdx
0x14000e670  jnz     short loc_14000E67E
0x14000e672  mov     [rcx], rdx
0x14000e675  mov     rax, rbx
0x14000e678  add     rsp, 20h
0x14000e67c  pop     rbx
0x14000e67d  retn
0x14000e67e  mov     rcx, rdx; psz
0x14000e681  call    cs:__imp_SysAllocString
0x14000e687  mov     [rbx], rax
0x14000e68a  test    rax, rax
0x14000e68d  jnz     short loc_14000E675
0x14000e68f  mov     ecx, 8007000Eh; int
0x14000e694  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
