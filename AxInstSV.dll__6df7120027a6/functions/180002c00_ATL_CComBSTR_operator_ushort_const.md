# ATL::CComBSTR::operator=(ushort const *)

- ea: `0x180002c00`
- end: `0x180002c54`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z`
- size: `84`
- prototype: `BSTR *__fastcall(BSTR *, const OLECHAR *)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002e78`
- `0x180003260`
- `0x1800038dc`
- `0x180006640`
- `0x180006a20`
- `0x180006c70`
- `0x180011d1c`

## callees

- `0x180002c00`
- `0x180003208`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002c26`
- `OLEAUT32!__imp_SysAllocString` at `0x180002c26`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c18`
- `OLEAUT32!__imp_SysFreeString` at `0x180002c18`

## pseudocode

```c
BSTR *__fastcall ATL::CComBSTR::operator=(BSTR *a1, const OLECHAR *a2)
{
  BSTR v4; // rax

  if ( a2 != *a1 )
  {
    SysFreeString(*a1);
    if ( a2 )
    {
      v4 = SysAllocString(a2);
      *a1 = v4;
      if ( !v4 )
        ATL::AtlThrowImpl(-2147024882);
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
0x180002c00  mov     [rsp+arg_0], rbx
0x180002c05  push    rdi
0x180002c06  sub     rsp, 20h
0x180002c0a  mov     rdi, rdx
0x180002c0d  mov     rbx, rcx
0x180002c10  cmp     rdx, [rcx]
0x180002c13  jz      short loc_180002C46
0x180002c15  mov     rcx, [rcx]; bstrString
0x180002c18  call    cs:__imp_SysFreeString
0x180002c1e  test    rdi, rdi
0x180002c21  jz      short loc_180002C3F
0x180002c23  mov     rcx, rdi; psz
0x180002c26  call    cs:__imp_SysAllocString
0x180002c2c  mov     [rbx], rax
0x180002c2f  test    rax, rax
0x180002c32  jnz     short loc_180002C46
0x180002c34  mov     ecx, 8007000Eh; int
0x180002c39  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002c3f  mov     qword ptr [rbx], 0
0x180002c46  mov     rax, rbx
0x180002c49  mov     rbx, [rsp+28h+arg_0]
0x180002c4e  add     rsp, 20h
0x180002c52  pop     rdi
0x180002c53  retn
```
