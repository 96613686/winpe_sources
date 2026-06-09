# ATL::CComBSTR::Copy(void)

- ea: `0x180012ccc`
- end: `0x180012cef`
- name: `?Copy@CComBSTR@ATL@@QEBAPEAGXZ`
- size: `35`
- prototype: `unsigned __int16 *__fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012040`
- `0x18001c0d4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180012ce8`
- `OLEAUT32!__imp_SysStringLen` at `0x180012cd8`
- `OLEAUT32!__imp_SysStringLen` at `0x180012cd8`

## pseudocode

```c
BSTR __fastcall ATL::CComBSTR::Copy(BSTR *this)
{
  UINT v2; // eax

  v2 = SysStringLen(*this);
  return SysAllocStringLen(*this, v2);
}

```

## disassembly

```asm
0x180012ccc  push    rbx
0x180012cce  sub     rsp, 20h
0x180012cd2  mov     rbx, rcx
0x180012cd5  mov     rcx, [rcx]; pbstr
0x180012cd8  call    cs:__imp_SysStringLen
0x180012cde  mov     rcx, [rbx]
0x180012ce1  mov     edx, eax
0x180012ce3  add     rsp, 20h
0x180012ce7  pop     rbx
0x180012ce8  jmp     cs:__imp_SysAllocStringLen
```
