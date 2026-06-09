# CGenerateComment::Add(ushort const *)

- ea: `0x14000f3f0`
- end: `0x14000f4a4`
- name: `?Add@CGenerateComment@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(CGenerateComment *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000c5b0`

## callees

- `0x14000f3f0`
- `0x14000f710`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000f40f`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f455`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f40f`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f455`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f43a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f480`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f43a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f480`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f420`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f466`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f420`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f466`

## pseudocode

```c
__int64 __fastcall CGenerateComment::Add(CGenerateComment *this, const unsigned __int16 *a2)
{
  ATL::CComBSTR *v2; // rdi
  UINT v3; // eax
  __int64 v4; // rdi
  unsigned int v5; // esi
  UINT v6; // eax
  __int64 v7; // rdi
  OLECHAR *v9; // [rsp+38h] [rbp+10h]
  OLECHAR *v10; // [rsp+38h] [rbp+10h]

  v2 = (CGenerateComment *)((char *)this + 8);
  if ( a2 )
  {
    v5 = 0;
    v10 = SysAllocString(a2);
    v6 = SysStringLen(v10);
    ATL::CComBSTR::Append(v2, v10, v6);
    v7 = *(_QWORD *)v2;
    SysFreeString(v10);
    if ( !v7 )
      return (unsigned int)-2147024882;
  }
  else
  {
    v9 = SysAllocString(L"\r\n");
    v3 = SysStringLen(v9);
    ATL::CComBSTR::Append(v2, v9, v3);
    v4 = *(_QWORD *)v2;
    SysFreeString(v9);
    return v4 == 0 ? 0x8007000E : 0;
  }
  return v5;
}

```

## disassembly

```asm
0x14000f3f0  mov     [rsp+arg_0], rbx
0x14000f3f5  mov     [rsp+arg_10], rsi
0x14000f3fa  push    rdi
0x14000f3fb  sub     rsp, 20h
0x14000f3ff  lea     rdi, [rcx+8]
0x14000f403  test    rdx, rdx
0x14000f406  jnz     short loc_14000F450
0x14000f408  lea     rcx, asc_14001B440; "\r\n"
0x14000f40f  call    cs:__imp_SysAllocString
0x14000f415  mov     rbx, rax
0x14000f418  mov     [rsp+28h+arg_8], rax
0x14000f41d  mov     rcx, rax; pbstr
0x14000f420  call    cs:__imp_SysStringLen
0x14000f426  mov     r8d, eax; int
0x14000f429  mov     rdx, rbx; unsigned __int16 *
0x14000f42c  mov     rcx, rdi; this
0x14000f42f  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14000f434  mov     rdi, [rdi]
0x14000f437  mov     rcx, rbx; bstrString
0x14000f43a  call    cs:__imp_SysFreeString
0x14000f440  nop
0x14000f441  neg     rdi
0x14000f444  sbb     esi, esi
0x14000f446  not     esi
0x14000f448  and     esi, 8007000Eh
0x14000f44e  jmp     short loc_14000F492
0x14000f450  xor     esi, esi
0x14000f452  mov     rcx, rdx; psz
0x14000f455  call    cs:__imp_SysAllocString
0x14000f45b  mov     rbx, rax
0x14000f45e  mov     [rsp+28h+arg_8], rax
0x14000f463  mov     rcx, rax; pbstr
0x14000f466  call    cs:__imp_SysStringLen
0x14000f46c  mov     r8d, eax; int
0x14000f46f  mov     rdx, rbx; unsigned __int16 *
0x14000f472  mov     rcx, rdi; this
0x14000f475  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14000f47a  mov     rdi, [rdi]
0x14000f47d  mov     rcx, rbx; bstrString
0x14000f480  call    cs:__imp_SysFreeString
0x14000f486  nop
0x14000f487  mov     eax, 8007000Eh
0x14000f48c  test    rdi, rdi
0x14000f48f  cmovz   esi, eax
0x14000f492  mov     eax, esi
0x14000f494  mov     rbx, [rsp+28h+arg_0]
0x14000f499  mov     rsi, [rsp+28h+arg_10]
0x14000f49e  add     rsp, 20h
0x14000f4a2  pop     rdi
0x14000f4a3  retn
```
