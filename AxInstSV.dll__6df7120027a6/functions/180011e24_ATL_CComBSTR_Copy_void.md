# ATL::CComBSTR::Copy(void)

- ea: `0x180011e24`
- end: `0x180011e54`
- name: `?Copy@CComBSTR@ATL@@QEBAPEAGXZ`
- size: `48`
- prototype: `BSTR __fastcall(LPCSTR *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800119a4`
- `0x180011ee0`

## callees

- `0x180011e24`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x180011e3d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180011e3d`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180011e4d`

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
0x180011e24  push    rbx
0x180011e26  sub     rsp, 20h
0x180011e2a  mov     rbx, rcx
0x180011e2d  mov     rcx, [rcx]; bstr
0x180011e30  test    rcx, rcx
0x180011e33  jnz     short loc_180011E3D
0x180011e35  xor     eax, eax
0x180011e37  add     rsp, 20h
0x180011e3b  pop     rbx
0x180011e3c  retn
0x180011e3d  call    cs:__imp_SysStringByteLen
0x180011e43  mov     rcx, [rbx]
0x180011e46  mov     edx, eax
0x180011e48  add     rsp, 20h
0x180011e4c  pop     rbx
0x180011e4d  jmp     cs:__imp_SysAllocStringByteLen
```
