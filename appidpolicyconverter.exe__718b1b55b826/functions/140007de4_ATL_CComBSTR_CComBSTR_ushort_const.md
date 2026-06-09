# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x140007de4`
- end: `0x140007e15`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `49`
- prototype: `ATL::CComBSTR *__fastcall(ATL::CComBSTR *this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400080e4`
- `0x140011d68`
- `0x140012278`
- `0x140012764`
- `0x140012e1c`
- `0x1400130ec`

## callees

- `0x140002b90`
- `0x140007de4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140007e01`
- `OLEAUT32!__imp_SysAllocString` at `0x140007e01`

## pseudocode

```c
ATL::CComBSTR *__fastcall ATL::CComBSTR::CComBSTR(ATL::CComBSTR *this, const unsigned __int16 *a2)
{
  BSTR v4; // rax
  int v5; // ecx

  if ( a2 )
  {
    v4 = SysAllocString(a2);
    *(_QWORD *)this = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(v5);
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
0x140007de4  push    rbx
0x140007de6  sub     rsp, 20h
0x140007dea  mov     rbx, rcx
0x140007ded  test    rdx, rdx
0x140007df0  jnz     short loc_140007DFE
0x140007df2  mov     [rcx], rdx
0x140007df5  mov     rax, rbx
0x140007df8  add     rsp, 20h
0x140007dfc  pop     rbx
0x140007dfd  retn
0x140007dfe  mov     rcx, rdx; psz
0x140007e01  call    cs:__imp_SysAllocString
0x140007e07  mov     [rbx], rax
0x140007e0a  test    rax, rax
0x140007e0d  jnz     short loc_140007DF5
0x140007e0f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
