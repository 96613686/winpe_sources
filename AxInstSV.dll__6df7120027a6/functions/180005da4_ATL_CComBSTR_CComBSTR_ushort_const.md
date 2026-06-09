# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x180005da4`
- end: `0x180005dda`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `54`
- prototype: `ATL::CComBSTR *__fastcall(ATL::CComBSTR *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005ee0`
- `0x180011d1c`
- `0x180011ee0`

## callees

- `0x180003208`
- `0x180005da4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180005dc1`
- `OLEAUT32!__imp_SysAllocString` at `0x180005dc1`

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
0x180005da4  push    rbx
0x180005da6  sub     rsp, 20h
0x180005daa  mov     rbx, rcx
0x180005dad  test    rdx, rdx
0x180005db0  jnz     short loc_180005DBE
0x180005db2  mov     [rcx], rdx
0x180005db5  mov     rax, rbx
0x180005db8  add     rsp, 20h
0x180005dbc  pop     rbx
0x180005dbd  retn
0x180005dbe  mov     rcx, rdx; psz
0x180005dc1  call    cs:__imp_SysAllocString
0x180005dc7  mov     [rbx], rax
0x180005dca  test    rax, rax
0x180005dcd  jnz     short loc_180005DB5
0x180005dcf  mov     ecx, 8007000Eh; int
0x180005dd4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
