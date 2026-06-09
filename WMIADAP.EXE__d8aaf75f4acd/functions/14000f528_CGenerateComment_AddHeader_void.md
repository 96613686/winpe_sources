# CGenerateComment::AddHeader(void)

- ea: `0x14000f528`
- end: `0x14000f588`
- name: `?AddHeader@CGenerateComment@@QEAAJXZ`
- size: `96`
- prototype: `__int64 __fastcall(CGenerateComment *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b9c8`
- `0x14000c5b0`
- `0x14000f4ac`

## callees

- `0x14000f710`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000f53c`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f53c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f566`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f566`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f54d`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f54d`

## pseudocode

```c
__int64 __fastcall CGenerateComment::AddHeader(CGenerateComment *this)
{
  UINT v2; // eax
  OLECHAR *v4; // [rsp+30h] [rbp+8h]

  v4 = SysAllocString(L"//////////////////////////////////////////////////////////////////////////////////////////////\r\n");
  v2 = SysStringLen(v4);
  ATL::CComBSTR::Append((CGenerateComment *)((char *)this + 8), v4, v2);
  SysFreeString(v4);
  return *((_QWORD *)this + 1) == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x14000f528  mov     [rsp+arg_8], rbx
0x14000f52d  push    rdi
0x14000f52e  sub     rsp, 20h
0x14000f532  mov     rdi, rcx
0x14000f535  lea     rcx, asc_14001BB60; "///////////////////////////////////////"...
0x14000f53c  call    cs:__imp_SysAllocString
0x14000f542  mov     rbx, rax
0x14000f545  mov     [rsp+28h+arg_0], rax
0x14000f54a  mov     rcx, rax; pbstr
0x14000f54d  call    cs:__imp_SysStringLen
0x14000f553  mov     r8d, eax; int
0x14000f556  mov     rdx, rbx; unsigned __int16 *
0x14000f559  lea     rcx, [rdi+8]; this
0x14000f55d  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14000f562  nop
0x14000f563  mov     rcx, rbx; bstrString
0x14000f566  call    cs:__imp_SysFreeString
0x14000f56c  nop
0x14000f56d  mov     rax, [rdi+8]
0x14000f571  neg     rax
0x14000f574  sbb     eax, eax
0x14000f576  not     eax
0x14000f578  and     eax, 8007000Eh
0x14000f57d  mov     rbx, [rsp+28h+arg_8]
0x14000f582  add     rsp, 20h
0x14000f586  pop     rdi
0x14000f587  retn
```
