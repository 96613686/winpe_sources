# _bstr_t::copy(void)

- ea: `0x18004c9dc`
- end: `0x18004ca1b`
- name: `?copy@_bstr_t@@QEBAPEAGXZ`
- size: `63`
- prototype: `unsigned __int16 *__fastcall(_bstr_t *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004ca90`
- `0x180056a50`
- `0x180057850`
- `0x180057bd0`
- `0x180057c50`
- `0x180059360`
- `0x1800594e0`
- `0x18005ab90`
- `0x18005acf0`

## callees

- `0x180003894`
- `0x18004c9dc`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x18004c9f2`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004c9f2`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18004c9fd`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18004c9fd`

## pseudocode

```c
BSTR __fastcall _bstr_t::copy(BSTR **this)
{
  BSTR *v1; // rbx
  UINT v2; // eax
  BSTR result; // rax

  v1 = *this;
  if ( !*this || !*v1 )
    return 0;
  v2 = SysStringByteLen(*v1);
  result = SysAllocStringByteLen((LPCSTR)*v1, v2);
  if ( !result )
    _com_issue_error(-2147024882);
  return result;
}

```

## disassembly

```asm
0x18004c9dc  push    rbx
0x18004c9de  sub     rsp, 20h
0x18004c9e2  mov     rbx, [rcx]
0x18004c9e5  test    rbx, rbx
0x18004c9e8  jz      short loc_18004CA13
0x18004c9ea  mov     rcx, [rbx]; bstr
0x18004c9ed  test    rcx, rcx
0x18004c9f0  jz      short loc_18004CA13
0x18004c9f2  call    cs:__imp_SysStringByteLen
0x18004c9f8  mov     rcx, [rbx]; psz
0x18004c9fb  mov     edx, eax; len
0x18004c9fd  call    cs:__imp_SysAllocStringByteLen
0x18004ca03  test    rax, rax
0x18004ca06  jnz     short loc_18004CA15
0x18004ca08  mov     ecx, 8007000Eh; int
0x18004ca0d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18004ca13  xor     eax, eax
0x18004ca15  add     rsp, 20h
0x18004ca19  pop     rbx
0x18004ca1a  retn
```
