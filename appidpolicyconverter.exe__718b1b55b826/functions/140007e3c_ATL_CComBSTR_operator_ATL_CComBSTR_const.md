# ATL::CComBSTR::operator=(ATL::CComBSTR const &)

- ea: `0x140007e3c`
- end: `0x140007e84`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z`
- size: `72`
- prototype: `OLECHAR **__fastcall(OLECHAR **, ATL::CComBSTR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140007edc`

## callees

- `0x140002b90`
- `0x140007e3c`
- `0x140007fe4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140007e54`
- `OLEAUT32!__imp_SysFreeString` at `0x140007e54`

## pseudocode

```c
OLECHAR **__fastcall ATL::CComBSTR::operator=(OLECHAR **a1, ATL::CComBSTR *a2)
{
  OLECHAR *v4; // rcx
  unsigned __int16 *v5; // rax
  int v6; // ecx

  v4 = *a1;
  if ( v4 != *(OLECHAR **)a2 )
  {
    SysFreeString(v4);
    v5 = ATL::CComBSTR::Copy(a2);
    *a1 = v5;
    if ( *(_QWORD *)a2 )
    {
      if ( !v5 )
        ATL::AtlThrowImpl(v6);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140007e3c  mov     [rsp+arg_0], rbx
0x140007e41  push    rdi
0x140007e42  sub     rsp, 20h
0x140007e46  mov     rbx, rcx
0x140007e49  mov     rdi, rdx
0x140007e4c  mov     rcx, [rcx]; bstrString
0x140007e4f  cmp     rcx, [rdx]
0x140007e52  jz      short loc_140007E76
0x140007e54  call    cs:__imp_SysFreeString
0x140007e5a  mov     rcx, rdi; this
0x140007e5d  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x140007e62  mov     [rbx], rax
0x140007e65  cmp     qword ptr [rdi], 0
0x140007e69  jz      short loc_140007E76
0x140007e6b  test    rax, rax
0x140007e6e  jnz     short loc_140007E76
0x140007e70  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140007e76  mov     rax, rbx
0x140007e79  mov     rbx, [rsp+28h+arg_0]
0x140007e7e  add     rsp, 20h
0x140007e82  pop     rdi
0x140007e83  retn
```
