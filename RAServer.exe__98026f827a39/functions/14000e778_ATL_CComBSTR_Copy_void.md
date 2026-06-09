# ATL::CComBSTR::Copy(void)

- ea: `0x14000e778`
- end: `0x14000e7a8`
- name: `?Copy@CComBSTR@ATL@@QEBAPEAGXZ`
- size: `48`
- prototype: `BSTR __fastcall(LPCSTR *this)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000f0b0`
- `0x14000f100`
- `0x14000f150`
- `0x1400117e0`
- `0x140011a4c`
- `0x140011fc0`
- `0x140012e70`
- `0x140013250`

## callees

- `0x14000e778`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x14000e791`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14000e791`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14000e7a1`

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
0x14000e778  push    rbx
0x14000e77a  sub     rsp, 20h
0x14000e77e  mov     rbx, rcx
0x14000e781  mov     rcx, [rcx]; bstr
0x14000e784  test    rcx, rcx
0x14000e787  jnz     short loc_14000E791
0x14000e789  xor     eax, eax
0x14000e78b  add     rsp, 20h
0x14000e78f  pop     rbx
0x14000e790  retn
0x14000e791  call    cs:__imp_SysStringByteLen
0x14000e797  mov     rcx, [rbx]
0x14000e79a  mov     edx, eax
0x14000e79c  add     rsp, 20h
0x14000e7a0  pop     rbx
0x14000e7a1  jmp     cs:__imp_SysAllocStringByteLen
```
