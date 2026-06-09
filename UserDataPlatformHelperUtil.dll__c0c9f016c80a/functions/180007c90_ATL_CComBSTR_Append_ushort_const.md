# ATL::CComBSTR::Append(ushort const *)

- ea: `0x180007c90`
- end: `0x180007d78`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBG@Z`
- size: `232`
- prototype: `__int64 __fastcall(BSTR *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007d80`
- `0x1800080d0`

## callees

- `0x180003ec0`
- `0x180007c90`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007cea`
- `msvcrt!memcpy_s` at `0x180007d1b`
- `msvcrt!memcpy_s` at `0x180007cea`
- `msvcrt!memcpy_s` at `0x180007d1b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180007cbd`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180007cbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180007d43`
- `OLEAUT32!__imp_SysFreeString` at `0x180007d43`
- `OLEAUT32!__imp_SysStringLen` at `0x180007c9f`
- `OLEAUT32!__imp_SysStringLen` at `0x180007cce`
- `OLEAUT32!__imp_SysStringLen` at `0x180007c9f`
- `OLEAUT32!__imp_SysStringLen` at `0x180007cce`

## pseudocode

```c
__int64 __fastcall ATL::CComBSTR::Append(BSTR *this, const unsigned __int16 *a2)
{
  signed int v3; // eax
  __int64 v4; // rsi
  signed int v5; // ebp
  __int64 result; // rax
  BSTR v7; // rdi
  errno_t v8; // eax
  errno_t v9; // eax

  v3 = SysStringLen(*this);
  v4 = v3;
  v5 = v3 + 1;
  if ( v3 + 1 < v3 )
    return 2147942414LL;
  v7 = SysAllocStringLen(0, v5);
  if ( !v7 )
    return 2147942414LL;
  if ( SysStringLen(*this) )
  {
    v8 = memcpy_s(v7, 2LL * v5, *this, 2 * v4);
    if ( v8 )
    {
      if ( v8 == 12 )
        goto LABEL_18;
      if ( v8 == 22 || v8 == 34 )
        goto LABEL_17;
      if ( v8 != 80 )
        goto LABEL_16;
    }
  }
  v9 = memcpy_s(&v7[v4], 2u, L";", 2u);
  if ( v9 )
  {
    if ( v9 != 12 )
    {
      if ( v9 != 22 && v9 != 34 )
      {
        if ( v9 == 80 )
          goto LABEL_15;
LABEL_16:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_17:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_18:
    ATL::AtlThrowImpl(-2147024882);
  }
LABEL_15:
  v7[v4 + 1] = 0;
  SysFreeString(*this);
  result = 0;
  *this = v7;
  return result;
}

```

## disassembly

```asm
0x180007c90  push    rbx
0x180007c92  push    rbp
0x180007c93  push    rsi
0x180007c94  push    rdi
0x180007c95  sub     rsp, 28h
0x180007c99  mov     rbx, rcx
0x180007c9c  mov     rcx, [rcx]; pbstr
0x180007c9f  call    cs:__imp_SysStringLen
0x180007ca5  movsxd  rsi, eax
0x180007ca8  lea     ebp, [rsi+1]
0x180007cab  cmp     ebp, esi
0x180007cad  jge     short loc_180007CB9
0x180007caf  mov     eax, 8007000Eh
0x180007cb4  jmp     loc_180007D4E
0x180007cb9  mov     edx, ebp; ui
0x180007cbb  xor     ecx, ecx; strIn
0x180007cbd  call    cs:__imp_SysAllocStringLen
0x180007cc3  mov     rdi, rax
0x180007cc6  test    rax, rax
0x180007cc9  jz      short loc_180007CAF
0x180007ccb  mov     rcx, [rbx]; pbstr
0x180007cce  call    cs:__imp_SysStringLen
0x180007cd4  test    eax, eax
0x180007cd6  jz      short loc_180007D08
0x180007cd8  mov     r8, [rbx]; Source
0x180007cdb  mov     r9, rsi
0x180007cde  movsxd  rdx, ebp
0x180007ce1  add     r9, r9; SourceSize
0x180007ce4  add     rdx, rdx; DestinationSize
0x180007ce7  mov     rcx, rdi; Destination
0x180007cea  call    cs:__imp_memcpy_s
0x180007cf0  test    eax, eax
0x180007cf2  jz      short loc_180007D08
0x180007cf4  cmp     eax, 0Ch
0x180007cf7  jz      short loc_180007D6D
0x180007cf9  cmp     eax, 16h
0x180007cfc  jz      short loc_180007D62
0x180007cfe  cmp     eax, 22h ; '"'
0x180007d01  jz      short loc_180007D62
0x180007d03  cmp     eax, 50h ; 'P'
0x180007d06  jnz     short loc_180007D57
0x180007d08  mov     edx, 2; DestinationSize
0x180007d0d  lea     rcx, [rdi+rsi*2]; Destination
0x180007d11  mov     r9d, edx; SourceSize
0x180007d14  lea     r8, asc_18000D13C; ";"
0x180007d1b  call    cs:__imp_memcpy_s
0x180007d21  test    eax, eax
0x180007d23  jz      short loc_180007D39
0x180007d25  cmp     eax, 0Ch
0x180007d28  jz      short loc_180007D6D
0x180007d2a  cmp     eax, 16h
0x180007d2d  jz      short loc_180007D62
0x180007d2f  cmp     eax, 22h ; '"'
0x180007d32  jz      short loc_180007D62
0x180007d34  cmp     eax, 50h ; 'P'
0x180007d37  jnz     short loc_180007D57
0x180007d39  xor     eax, eax
0x180007d3b  mov     [rdi+rsi*2+2], ax
0x180007d40  mov     rcx, [rbx]; bstrString
0x180007d43  call    cs:__imp_SysFreeString
0x180007d49  xor     eax, eax
0x180007d4b  mov     [rbx], rdi
0x180007d4e  add     rsp, 28h
0x180007d52  pop     rdi
0x180007d53  pop     rsi
0x180007d54  pop     rbp
0x180007d55  pop     rbx
0x180007d56  retn
0x180007d57  mov     ecx, 80004005h; int
0x180007d5c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007d62  mov     ecx, 80070057h; int
0x180007d67  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007d6d  mov     ecx, 8007000Eh; int
0x180007d72  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
