# ATL::CComBSTR::operator=(ushort const *)

- ea: `0x14000e6a0`
- end: `0x14000e6f4`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z`
- size: `84`
- prototype: `BSTR *__fastcall(BSTR *, const OLECHAR *)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e904`
- `0x14000f1c0`
- `0x14000f210`
- `0x14000f260`
- `0x140013250`
- `0x140013c10`
- `0x140013ef8`
- `0x140014618`
- `0x140014740`
- `0x140014ccc`

## callees

- `0x140004f54`
- `0x14000e6a0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000e6c6`
- `OLEAUT32!__imp_SysAllocString` at `0x14000e6c6`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e6b8`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e6b8`

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
0x14000e6a0  mov     [rsp+arg_0], rbx
0x14000e6a5  push    rdi
0x14000e6a6  sub     rsp, 20h
0x14000e6aa  mov     rdi, rdx
0x14000e6ad  mov     rbx, rcx
0x14000e6b0  cmp     rdx, [rcx]
0x14000e6b3  jz      short loc_14000E6E6
0x14000e6b5  mov     rcx, [rcx]; bstrString
0x14000e6b8  call    cs:__imp_SysFreeString
0x14000e6be  test    rdi, rdi
0x14000e6c1  jz      short loc_14000E6DF
0x14000e6c3  mov     rcx, rdi; psz
0x14000e6c6  call    cs:__imp_SysAllocString
0x14000e6cc  mov     [rbx], rax
0x14000e6cf  test    rax, rax
0x14000e6d2  jnz     short loc_14000E6E6
0x14000e6d4  mov     ecx, 8007000Eh; int
0x14000e6d9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000e6df  mov     qword ptr [rbx], 0
0x14000e6e6  mov     rax, rbx
0x14000e6e9  mov     rbx, [rsp+28h+arg_0]
0x14000e6ee  add     rsp, 20h
0x14000e6f2  pop     rdi
0x14000e6f3  retn
```
