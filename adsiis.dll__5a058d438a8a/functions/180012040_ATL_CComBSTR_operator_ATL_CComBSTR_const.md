# ATL::CComBSTR::operator=(ATL::CComBSTR const &)

- ea: `0x180012040`
- end: `0x18001207c`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012574`
- `0x18001c4b8`

## callees

- `0x180012040`
- `0x180012ccc`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001205d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001205d`

## pseudocode

```c
OLECHAR **__fastcall ATL::CComBSTR::operator=(OLECHAR **a1, ATL::CComBSTR *a2)
{
  OLECHAR *v4; // rcx

  v4 = *a1;
  if ( v4 != *(OLECHAR **)a2 )
  {
    if ( v4 )
      SysFreeString(v4);
    *a1 = ATL::CComBSTR::Copy(a2);
  }
  return a1;
}

```

## disassembly

```asm
0x180012040  mov     [rsp+arg_0], rbx
0x180012045  push    rdi
0x180012046  sub     rsp, 20h
0x18001204a  mov     rbx, rcx
0x18001204d  mov     rdi, rdx
0x180012050  mov     rcx, [rcx]; bstrString
0x180012053  cmp     rcx, [rdx]
0x180012056  jz      short loc_18001206E
0x180012058  test    rcx, rcx
0x18001205b  jz      short loc_180012063
0x18001205d  call    cs:__imp_SysFreeString
0x180012063  mov     rcx, rdi; this
0x180012066  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x18001206b  mov     [rbx], rax
0x18001206e  mov     rax, rbx
0x180012071  mov     rbx, [rsp+28h+arg_0]
0x180012076  add     rsp, 20h
0x18001207a  pop     rdi
0x18001207b  retn
```
