# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x18001d358`
- end: `0x18001d395`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `61`
- prototype: `_QWORD(ATL::CComBSTR *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ec34`
- `0x180020020`
- `0x1800202b0`
- `0x180020410`
- `0x1800213a4`
- `0x180024248`

## callees

- `0x180015f4c`
- `0x18001d358`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001d376`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d376`

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
0x18001d358  push    rbx
0x18001d35a  sub     rsp, 20h
0x18001d35e  mov     rbx, rcx
0x18001d361  test    rdx, rdx
0x18001d364  jnz     short loc_18001D373
0x18001d366  and     [rcx], rdx
0x18001d369  mov     rax, rbx
0x18001d36c  add     rsp, 20h
0x18001d370  pop     rbx
0x18001d371  retn
0x18001d373  mov     rcx, rdx; psz
0x18001d376  call    cs:__imp_SysAllocString
0x18001d37d  nop     dword ptr [rax+rax+00h]
0x18001d382  mov     [rbx], rax
0x18001d385  test    rax, rax
0x18001d388  jnz     short loc_18001D369
0x18001d38a  mov     ecx, 8007000Eh; int
0x18001d38f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
