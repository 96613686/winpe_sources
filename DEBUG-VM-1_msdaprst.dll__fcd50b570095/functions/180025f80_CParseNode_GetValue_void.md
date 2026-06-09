# CParseNode::GetValue(void)

- ea: `0x180025f80`
- end: `0x180025f92`
- name: `?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ`
- size: `18`
- prototype: `struct ATL::CComBSTR *__fastcall(CParseNode *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180023730`
- `0x180023bbc`
- `0x180025d2c`
- `0x180026810`
- `0x18002769c`
- `0x180027944`

## callees

- `0x180025f80`

## pseudocode

```c
struct ATL::CComBSTR *__fastcall CParseNode::GetValue(CParseNode *this)
{
  struct ATL::CComBSTR *result; // rax

  result = (CParseNode *)((char *)this + 48);
  if ( !*((_QWORD *)this + 6) )
    return (struct ATL::CComBSTR *)&CParseNode::s_bstrZLS;
  return result;
}

```

## disassembly

```asm
0x180025f80  lea     rax, [rcx+30h]
0x180025f84  cmp     qword ptr [rax], 0
0x180025f88  jnz     short locret_180025F91
0x180025f8a  lea     rax, ?s_bstrZLS@CParseNode@@0VCComBSTR@ATL@@A; ATL::CComBSTR CParseNode::s_bstrZLS
0x180025f91  retn
```
