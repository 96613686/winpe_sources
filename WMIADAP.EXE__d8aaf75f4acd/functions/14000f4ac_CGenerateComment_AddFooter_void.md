# CGenerateComment::AddFooter(void)

- ea: `0x14000f4ac`
- end: `0x14000f521`
- name: `?AddFooter@CGenerateComment@@QEAAJXZ`
- size: `117`
- prototype: `__int64 __fastcall(CGenerateComment *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b9c8`
- `0x14000c5b0`

## callees

- `0x14000f4ac`
- `0x14000f528`
- `0x14000f710`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000f4d0`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f4d0`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f4fd`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f4fd`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f4e1`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f4e1`

## pseudocode

```c
__int64 __fastcall CGenerateComment::AddFooter(CGenerateComment *this)
{
  int v2; // esi
  UINT v3; // eax
  __int64 v4; // rdi
  OLECHAR *v6; // [rsp+38h] [rbp+10h]

  v2 = CGenerateComment::AddHeader(this);
  if ( v2 >= 0 )
  {
    v6 = SysAllocString(L"\r\n");
    v3 = SysStringLen(v6);
    ATL::CComBSTR::Append((CGenerateComment *)((char *)this + 8), v6, v3);
    v4 = *((_QWORD *)this + 1);
    SysFreeString(v6);
    if ( !v4 )
      return (unsigned int)-2147024882;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000f4ac  mov     [rsp+arg_0], rbx
0x14000f4b1  mov     [rsp+arg_10], rsi
0x14000f4b6  push    rdi
0x14000f4b7  sub     rsp, 20h
0x14000f4bb  mov     rdi, rcx
0x14000f4be  call    ?AddHeader@CGenerateComment@@QEAAJXZ; CGenerateComment::AddHeader(void)
0x14000f4c3  mov     esi, eax
0x14000f4c5  test    eax, eax
0x14000f4c7  js      short loc_14000F50F
0x14000f4c9  lea     rcx, asc_14001B440; "\r\n"
0x14000f4d0  call    cs:__imp_SysAllocString
0x14000f4d6  mov     rbx, rax
0x14000f4d9  mov     [rsp+28h+arg_8], rax
0x14000f4de  mov     rcx, rax; pbstr
0x14000f4e1  call    cs:__imp_SysStringLen
0x14000f4e7  mov     r8d, eax; int
0x14000f4ea  mov     rdx, rbx; unsigned __int16 *
0x14000f4ed  lea     rcx, [rdi+8]; this
0x14000f4f1  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14000f4f6  mov     rdi, [rdi+8]
0x14000f4fa  mov     rcx, rbx; bstrString
0x14000f4fd  call    cs:__imp_SysFreeString
0x14000f503  nop
0x14000f504  mov     eax, 8007000Eh
0x14000f509  test    rdi, rdi
0x14000f50c  cmovz   esi, eax
0x14000f50f  mov     eax, esi
0x14000f511  mov     rbx, [rsp+28h+arg_0]
0x14000f516  mov     rsi, [rsp+28h+arg_10]
0x14000f51b  add     rsp, 20h
0x14000f51f  pop     rdi
0x14000f520  retn
```
