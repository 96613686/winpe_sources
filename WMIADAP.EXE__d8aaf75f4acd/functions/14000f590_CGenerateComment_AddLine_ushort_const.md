# CGenerateComment::AddLine(ushort const *)

- ea: `0x14000f590`
- end: `0x14000f709`
- name: `?AddLine@CGenerateComment@@QEAAJPEBG@Z`
- size: `377`
- prototype: `__int64 __fastcall(CGenerateComment *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b9c8`
- `0x14000c5b0`

## callees

- `0x14000f590`
- `0x14000f710`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000f5fe`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000f614`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000f5fe`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000f614`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f5b2`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f63a`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f678`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f6bd`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f5b2`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f63a`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f678`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f6bd`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f5df`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f669`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f6a3`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f6e8`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f5df`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f669`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f6a3`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f6e8`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f5c3`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f64f`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f689`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f6ce`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f5c3`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f64f`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f689`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f6ce`

## pseudocode

```c
__int64 __fastcall CGenerateComment::AddLine(CGenerateComment *this, const unsigned __int16 *a2)
{
  UINT v4; // eax
  __int64 v5; // rdi
  int v6; // esi
  LPWSTR v7; // rax
  WCHAR v8; // cx
  ATL::CComBSTR *v9; // r14
  UINT v10; // eax
  __int64 v11; // rdi
  UINT v12; // eax
  __int64 v13; // rdi
  UINT v14; // eax
  __int64 v15; // rdi
  OLECHAR *v17; // [rsp+68h] [rbp+10h]
  OLECHAR *v18; // [rsp+68h] [rbp+10h]
  OLECHAR *v19; // [rsp+68h] [rbp+10h]
  OLECHAR *v20; // [rsp+68h] [rbp+10h]

  if ( a2 )
  {
    v6 = 0;
    v7 = CharNextW(a2);
    if ( !v7 )
      goto LABEL_10;
    v8 = *v7;
    while ( v8 )
    {
      v7 = CharNextW(v7);
      v8 = *v7;
      if ( *v7 == 10 )
        v6 = -2147024809;
    }
    if ( v6 >= 0 )
    {
LABEL_10:
      v18 = SysAllocString(L"// ");
      v9 = (CGenerateComment *)((char *)this + 8);
      v10 = SysStringLen(v18);
      ATL::CComBSTR::Append(v9, v18, v10);
      v11 = *(_QWORD *)v9;
      SysFreeString(v18);
      if ( v11
        && (v19 = SysAllocString(a2),
            v12 = SysStringLen(v19),
            ATL::CComBSTR::Append(v9, v19, v12),
            v13 = *(_QWORD *)v9,
            SysFreeString(v19),
            v13) )
      {
        v20 = SysAllocString(L"\r\n");
        v14 = SysStringLen(v20);
        ATL::CComBSTR::Append(v9, v20, v14);
        v15 = *(_QWORD *)v9;
        SysFreeString(v20);
        if ( !v15 )
          return (unsigned int)-2147024882;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    v17 = SysAllocString(L"//\r\n");
    v4 = SysStringLen(v17);
    ATL::CComBSTR::Append((CGenerateComment *)((char *)this + 8), v17, v4);
    v5 = *((_QWORD *)this + 1);
    SysFreeString(v17);
    return v5 == 0 ? 0x8007000E : 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000f590  push    rbx
0x14000f592  push    rbp
0x14000f593  push    rsi
0x14000f594  push    rdi
0x14000f595  push    r14
0x14000f597  push    r15
0x14000f599  sub     rsp, 28h
0x14000f59d  mov     rbp, rdx
0x14000f5a0  mov     r14, rcx
0x14000f5a3  xor     r15d, r15d
0x14000f5a6  test    rdx, rdx
0x14000f5a9  jnz     short loc_14000F5F8
0x14000f5ab  lea     rcx, asc_14001BC28; "//\r\n"
0x14000f5b2  call    cs:__imp_SysAllocString
0x14000f5b8  mov     rbx, rax
0x14000f5bb  mov     [rsp+58h+arg_8], rax
0x14000f5c0  mov     rcx, rax; pbstr
0x14000f5c3  call    cs:__imp_SysStringLen
0x14000f5c9  mov     r8d, eax; int
0x14000f5cc  mov     rdx, rbx; unsigned __int16 *
0x14000f5cf  lea     rcx, [r14+8]; this
0x14000f5d3  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14000f5d8  mov     rdi, [r14+8]
0x14000f5dc  mov     rcx, rbx; bstrString
0x14000f5df  call    cs:__imp_SysFreeString
0x14000f5e5  nop
0x14000f5e6  neg     rdi
0x14000f5e9  sbb     esi, esi
0x14000f5eb  not     esi
0x14000f5ed  and     esi, 8007000Eh
0x14000f5f3  jmp     loc_14000F6FA
0x14000f5f8  mov     esi, r15d
0x14000f5fb  mov     rcx, rbp; lpsz
0x14000f5fe  call    cs:__imp_CharNextW
0x14000f604  test    rax, rax
0x14000f607  jz      short loc_14000F633
0x14000f609  movzx   ecx, word ptr [rax]
0x14000f60c  test    cx, cx
0x14000f60f  jz      short loc_14000F62B
0x14000f611  mov     rcx, rax; lpsz
0x14000f614  call    cs:__imp_CharNextW
0x14000f61a  movzx   ecx, word ptr [rax]
0x14000f61d  mov     edx, 80070057h
0x14000f622  cmp     cx, 0Ah
0x14000f626  cmovz   esi, edx
0x14000f629  jmp     short loc_14000F60C
0x14000f62b  test    esi, esi
0x14000f62d  js      loc_14000F6FA
0x14000f633  lea     rcx, asc_14001BC38; "// "
0x14000f63a  call    cs:__imp_SysAllocString
0x14000f640  mov     rbx, rax
0x14000f643  mov     [rsp+58h+arg_8], rax
0x14000f648  add     r14, 8
0x14000f64c  mov     rcx, rax; pbstr
0x14000f64f  call    cs:__imp_SysStringLen
0x14000f655  mov     r8d, eax; int
0x14000f658  mov     rdx, rbx; unsigned __int16 *
0x14000f65b  mov     rcx, r14; this
0x14000f65e  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14000f663  mov     rdi, [r14]
0x14000f666  mov     rcx, rbx; bstrString
0x14000f669  call    cs:__imp_SysFreeString
0x14000f66f  nop
0x14000f670  test    rdi, rdi
0x14000f673  jz      short loc_14000F6AF
0x14000f675  mov     rcx, rbp; psz
0x14000f678  call    cs:__imp_SysAllocString
0x14000f67e  mov     rbx, rax
0x14000f681  mov     [rsp+58h+arg_8], rax
0x14000f686  mov     rcx, rax; pbstr
0x14000f689  call    cs:__imp_SysStringLen
0x14000f68f  mov     r8d, eax; int
0x14000f692  mov     rdx, rbx; unsigned __int16 *
0x14000f695  mov     rcx, r14; this
0x14000f698  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14000f69d  mov     rdi, [r14]
0x14000f6a0  mov     rcx, rbx; bstrString
0x14000f6a3  call    cs:__imp_SysFreeString
0x14000f6a9  nop
0x14000f6aa  test    rdi, rdi
0x14000f6ad  jnz     short loc_14000F6B6
0x14000f6af  mov     esi, 8007000Eh
0x14000f6b4  jmp     short loc_14000F6FA
0x14000f6b6  lea     rcx, asc_14001B440; "\r\n"
0x14000f6bd  call    cs:__imp_SysAllocString
0x14000f6c3  mov     rbx, rax
0x14000f6c6  mov     [rsp+58h+arg_8], rax
0x14000f6cb  mov     rcx, rax; pbstr
0x14000f6ce  call    cs:__imp_SysStringLen
0x14000f6d4  mov     r8d, eax; int
0x14000f6d7  mov     rdx, rbx; unsigned __int16 *
0x14000f6da  mov     rcx, r14; this
0x14000f6dd  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14000f6e2  mov     rdi, [r14]
0x14000f6e5  mov     rcx, rbx; bstrString
0x14000f6e8  call    cs:__imp_SysFreeString
0x14000f6ee  nop
0x14000f6ef  mov     eax, 8007000Eh
0x14000f6f4  test    rdi, rdi
0x14000f6f7  cmovz   esi, eax
0x14000f6fa  mov     eax, esi
0x14000f6fc  add     rsp, 28h
0x14000f700  pop     r15
0x14000f702  pop     r14
0x14000f704  pop     rdi
0x14000f705  pop     rsi
0x14000f706  pop     rbp
0x14000f707  pop     rbx
0x14000f708  retn
```
