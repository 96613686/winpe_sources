# ATL::CComBSTR::Copy(void)

- ea: `0x140007fe4`
- end: `0x140008011`
- name: `?Copy@CComBSTR@ATL@@QEBAPEAGXZ`
- size: `45`
- prototype: `BSTR __fastcall(LPCSTR *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140007e3c`

## callees

- `0x140007fe4`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x140007ff9`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140007ff9`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140008004`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140008004`

## pseudocode

```c
BSTR __fastcall ATL::CComBSTR::Copy(LPCSTR *this)
{
  CHAR *v2; // rcx
  UINT v4; // eax

  v2 = (CHAR *)*this;
  if ( !v2 )
    return 0;
  v4 = SysStringByteLen((BSTR)v2);
  return SysAllocStringByteLen(*this, v4);
}

```

## disassembly

```asm
0x140007fe4  push    rbx
0x140007fe6  sub     rsp, 20h
0x140007fea  mov     rbx, rcx
0x140007fed  mov     rcx, [rcx]; bstr
0x140007ff0  test    rcx, rcx
0x140007ff3  jnz     short loc_140007FF9
0x140007ff5  xor     eax, eax
0x140007ff7  jmp     short loc_14000800B
0x140007ff9  call    cs:__imp_SysStringByteLen
0x140007fff  mov     edx, eax; len
0x140008001  mov     rcx, [rbx]; psz
0x140008004  call    cs:__imp_SysAllocStringByteLen
0x14000800a  nop
0x14000800b  add     rsp, 20h
0x14000800f  pop     rbx
0x140008010  retn
```
