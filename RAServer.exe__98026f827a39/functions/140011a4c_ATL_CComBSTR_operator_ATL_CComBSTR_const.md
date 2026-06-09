# ATL::CComBSTR::operator=(ATL::CComBSTR const &)

- ea: `0x140011a4c`
- end: `0x140011a99`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z`
- size: `77`
- prototype: `OLECHAR **__fastcall(OLECHAR **, ATL::CComBSTR *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140011fc0`
- `0x140013c10`

## callees

- `0x140004f54`
- `0x14000e778`
- `0x140011a4c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140011a64`
- `OLEAUT32!__imp_SysFreeString` at `0x140011a64`

## pseudocode

```c
OLECHAR **__fastcall ATL::CComBSTR::operator=(OLECHAR **a1, ATL::CComBSTR *a2)
{
  OLECHAR *v4; // rcx
  unsigned __int16 *v5; // rax

  v4 = *a1;
  if ( v4 != *(OLECHAR **)a2 )
  {
    SysFreeString(v4);
    v5 = ATL::CComBSTR::Copy(a2);
    *a1 = v5;
    if ( *(_QWORD *)a2 )
    {
      if ( !v5 )
        ATL::AtlThrowImpl(-2147024882);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140011a4c  mov     [rsp+arg_0], rbx
0x140011a51  push    rdi
0x140011a52  sub     rsp, 20h
0x140011a56  mov     rbx, rcx
0x140011a59  mov     rdi, rdx
0x140011a5c  mov     rcx, [rcx]; bstrString
0x140011a5f  cmp     rcx, [rdx]
0x140011a62  jz      short loc_140011A8B
0x140011a64  call    cs:__imp_SysFreeString
0x140011a6a  mov     rcx, rdi; this
0x140011a6d  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x140011a72  mov     [rbx], rax
0x140011a75  cmp     qword ptr [rdi], 0
0x140011a79  jz      short loc_140011A8B
0x140011a7b  test    rax, rax
0x140011a7e  jnz     short loc_140011A8B
0x140011a80  mov     ecx, 8007000Eh; int
0x140011a85  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140011a8b  mov     rax, rbx
0x140011a8e  mov     rbx, [rsp+28h+arg_0]
0x140011a93  add     rsp, 20h
0x140011a97  pop     rdi
0x140011a98  retn
```
