# ATL::CComBSTR::Append(ushort const *,int)

- ea: `0x1400139b4`
- end: `0x140013a7f`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBGH@Z`
- size: `203`
- prototype: `__int64 __fastcall(const void **this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001398c`

## callees

- `0x140004d30`
- `0x1400139b4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140013a29`
- `msvcrt!memcpy_s` at `0x140013a46`
- `msvcrt!memcpy_s` at `0x140013a29`
- `msvcrt!memcpy_s` at `0x140013a46`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400139fc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400139fc`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a60`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a60`
- `OLEAUT32!__imp_SysStringLen` at `0x1400139e4`
- `OLEAUT32!__imp_SysStringLen` at `0x140013a0d`
- `OLEAUT32!__imp_SysStringLen` at `0x1400139e4`
- `OLEAUT32!__imp_SysStringLen` at `0x140013a0d`

## pseudocode

```c
__int64 __fastcall ATL::CComBSTR::Append(const void **this, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rbp
  OLECHAR *v6; // rcx
  signed int v7; // eax
  __int64 v8; // rsi
  signed int v9; // edi
  BSTR v10; // r14
  errno_t v11; // eax
  errno_t v12; // eax

  v3 = a3;
  if ( !a2 )
    return 0;
  v6 = (OLECHAR *)*this;
  if ( v6 )
  {
    if ( !a3 )
      return 0;
  }
  v7 = SysStringLen(v6);
  v8 = v7;
  v9 = v7 + v3;
  if ( v7 + (int)v3 >= v7 )
  {
    v10 = SysAllocStringLen(0, v9);
    if ( v10 )
    {
      if ( SysStringLen((BSTR)*this) )
      {
        v11 = memcpy_s(v10, 2LL * v9, *this, 2 * v8);
        ATL::AtlCrtErrorCheck(v11);
      }
      v12 = memcpy_s(&v10[v8], 2 * v3, a2, 2 * v3);
      ATL::AtlCrtErrorCheck(v12);
      v10[v9] = 0;
      SysFreeString((BSTR)*this);
      *this = v10;
      return 0;
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1400139b4  push    rbx
0x1400139b6  push    rbp
0x1400139b7  push    rsi
0x1400139b8  push    rdi
0x1400139b9  push    r14
0x1400139bb  push    r15
0x1400139bd  sub     rsp, 28h
0x1400139c1  movsxd  rbp, r8d
0x1400139c4  mov     r15, rdx
0x1400139c7  mov     rbx, rcx
0x1400139ca  test    rdx, rdx
0x1400139cd  jz      loc_140013A69
0x1400139d3  mov     rcx, [rcx]; pbstr
0x1400139d6  test    rcx, rcx
0x1400139d9  jz      short loc_1400139E4
0x1400139db  test    r8d, r8d
0x1400139de  jz      loc_140013A69
0x1400139e4  call    cs:__imp_SysStringLen
0x1400139ea  movsxd  rsi, eax
0x1400139ed  lea     edi, [rsi+rbp]
0x1400139f0  cmp     edi, esi
0x1400139f2  jl      loc_140013A78
0x1400139f8  mov     edx, edi; ui
0x1400139fa  xor     ecx, ecx; strIn
0x1400139fc  call    cs:__imp_SysAllocStringLen
0x140013a02  mov     r14, rax
0x140013a05  test    rax, rax
0x140013a08  jz      short loc_140013A78
0x140013a0a  mov     rcx, [rbx]; pbstr
0x140013a0d  call    cs:__imp_SysStringLen
0x140013a13  test    eax, eax
0x140013a15  jz      short loc_140013A36
0x140013a17  mov     r9, rsi
0x140013a1a  add     r9, r9; SourceSize
0x140013a1d  movsxd  rdx, edi
0x140013a20  add     rdx, rdx; DestinationSize
0x140013a23  mov     r8, [rbx]; Source
0x140013a26  mov     rcx, r14; Destination
0x140013a29  call    cs:__imp_memcpy_s
0x140013a2f  mov     ecx, eax; int
0x140013a31  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140013a36  mov     rdx, rbp
0x140013a39  add     rdx, rdx; DestinationSize
0x140013a3c  lea     rcx, [r14+rsi*2]; Destination
0x140013a40  mov     r9, rdx; SourceSize
0x140013a43  mov     r8, r15; Source
0x140013a46  call    cs:__imp_memcpy_s
0x140013a4c  mov     ecx, eax; int
0x140013a4e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140013a53  movsxd  rcx, edi
0x140013a56  xor     eax, eax
0x140013a58  mov     [r14+rcx*2], ax
0x140013a5d  mov     rcx, [rbx]; bstrString
0x140013a60  call    cs:__imp_SysFreeString
0x140013a66  mov     [rbx], r14
0x140013a69  xor     eax, eax
0x140013a6b  add     rsp, 28h
0x140013a6f  pop     r15
0x140013a71  pop     r14
0x140013a73  pop     rdi
0x140013a74  pop     rsi
0x140013a75  pop     rbp
0x140013a76  pop     rbx
0x140013a77  retn
0x140013a78  mov     eax, 8007000Eh
0x140013a7d  jmp     short loc_140013A6B
```
