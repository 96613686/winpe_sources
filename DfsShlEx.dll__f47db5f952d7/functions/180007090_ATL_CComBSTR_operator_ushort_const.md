# ATL::CComBSTR::operator+=(ushort const *)

- ea: `0x180007090`
- end: `0x1800071ca`
- name: `??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z`
- size: `314`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007368`
- `0x180008eac`
- `0x180009700`

## callees

- `0x180004328`
- `0x180007090`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007126`
- `msvcrt!memcpy_s` at `0x180007158`
- `msvcrt!memcpy_s` at `0x180007126`
- `msvcrt!memcpy_s` at `0x180007158`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800070f9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800070f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180007181`
- `OLEAUT32!__imp_SysFreeString` at `0x180007181`
- `OLEAUT32!__imp_SysStringLen` at `0x1800070d9`
- `OLEAUT32!__imp_SysStringLen` at `0x18000710a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800070d9`
- `OLEAUT32!__imp_SysStringLen` at `0x18000710a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const void **__fastcall ATL::CComBSTR::operator+=(const void **a1, _WORD *a2)
{
  __int64 v4; // rbx
  OLECHAR *v5; // rcx
  signed int v6; // eax
  __int64 v7; // r15
  signed int v8; // ebp
  int v9; // ecx
  BSTR v10; // r14
  errno_t v11; // eax
  errno_t v12; // eax

  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
  }
  else
  {
    LODWORD(v4) = 0;
  }
  if ( !a2 )
    goto LABEL_23;
  v5 = (OLECHAR *)*a1;
  if ( v5 )
  {
    if ( !(_DWORD)v4 )
      goto LABEL_23;
  }
  v6 = SysStringLen(v5);
  v7 = v6;
  v8 = v6 + v4;
  if ( v6 + (int)v4 < v6 || (v10 = SysAllocStringLen(0, v8)) == 0 )
  {
    v9 = -2147024882;
    goto LABEL_24;
  }
  if ( SysStringLen((BSTR)*a1) )
  {
    v11 = memcpy_s(v10, 2LL * v8, *a1, 2 * v7);
    if ( v11 )
    {
      if ( v11 == 12 )
        goto LABEL_29;
      if ( v11 == 22 || v11 == 34 )
        goto LABEL_28;
      if ( v11 != 80 )
        goto LABEL_27;
    }
  }
  v12 = memcpy_s(&v10[v7], 2LL * (int)v4, a2, 2LL * (int)v4);
  if ( v12 )
  {
    if ( v12 != 12 )
    {
      if ( v12 != 22 && v12 != 34 )
      {
        if ( v12 == 80 )
          goto LABEL_22;
LABEL_27:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_28:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_29:
    ATL::AtlThrowImpl(-2147024882);
  }
LABEL_22:
  v10[v8] = 0;
  SysFreeString((BSTR)*a1);
  *a1 = v10;
LABEL_23:
  v9 = 0;
LABEL_24:
  if ( v9 < 0 )
    ATL::AtlThrowImpl(v9);
  return a1;
}

```

## disassembly

```asm
0x180007090  push    rbx
0x180007092  push    rbp
0x180007093  push    rsi
0x180007094  push    rdi
0x180007095  push    r12
0x180007097  push    r14
0x180007099  push    r15
0x18000709b  sub     rsp, 20h
0x18000709f  mov     rsi, rdx
0x1800070a2  mov     rdi, rcx
0x1800070a5  xor     r12d, r12d
0x1800070a8  test    rdx, rdx
0x1800070ab  jnz     short loc_1800070B2
0x1800070ad  mov     ebx, r12d
0x1800070b0  jmp     short loc_1800070C0
0x1800070b2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800070b6  inc     rbx
0x1800070b9  cmp     [rdx+rbx*2], r12w
0x1800070be  jnz     short loc_1800070B6
0x1800070c0  test    rsi, rsi
0x1800070c3  jz      loc_18000718A
0x1800070c9  mov     rcx, [rcx]; pbstr
0x1800070cc  test    rcx, rcx
0x1800070cf  jz      short loc_1800070D9
0x1800070d1  test    ebx, ebx
0x1800070d3  jz      loc_18000718A
0x1800070d9  call    cs:__imp_SysStringLen
0x1800070df  movsxd  r15, eax
0x1800070e2  lea     ebp, [r15+rbx]
0x1800070e6  cmp     ebp, r15d
0x1800070e9  jge     short loc_1800070F5
0x1800070eb  mov     ecx, 8007000Eh
0x1800070f0  jmp     loc_18000718D
0x1800070f5  mov     edx, ebp; ui
0x1800070f7  xor     ecx, ecx; strIn
0x1800070f9  call    cs:__imp_SysAllocStringLen
0x1800070ff  mov     r14, rax
0x180007102  test    rax, rax
0x180007105  jz      short loc_1800070EB
0x180007107  mov     rcx, [rdi]; pbstr
0x18000710a  call    cs:__imp_SysStringLen
0x180007110  test    eax, eax
0x180007112  jz      short loc_180007148
0x180007114  mov     r9, r15
0x180007117  add     r9, r9; SourceSize
0x18000711a  movsxd  rdx, ebp
0x18000711d  add     rdx, rdx; DestinationSize
0x180007120  mov     r8, [rdi]; Source
0x180007123  mov     rcx, r14; Destination
0x180007126  call    cs:__imp_memcpy_s
0x18000712c  test    eax, eax
0x18000712e  jz      short loc_180007148
0x180007130  cmp     eax, 0Ch
0x180007133  jz      loc_1800071BF
0x180007139  cmp     eax, 16h
0x18000713c  jz      short loc_1800071B4
0x18000713e  cmp     eax, 22h ; '"'
0x180007141  jz      short loc_1800071B4
0x180007143  cmp     eax, 50h ; 'P'
0x180007146  jnz     short loc_1800071A9
0x180007148  movsxd  rdx, ebx
0x18000714b  add     rdx, rdx; DestinationSize
0x18000714e  lea     rcx, [r14+r15*2]; Destination
0x180007152  mov     r9, rdx; SourceSize
0x180007155  mov     r8, rsi; Source
0x180007158  call    cs:__imp_memcpy_s
0x18000715e  test    eax, eax
0x180007160  jz      short loc_180007176
0x180007162  cmp     eax, 0Ch
0x180007165  jz      short loc_1800071BF
0x180007167  cmp     eax, 16h
0x18000716a  jz      short loc_1800071B4
0x18000716c  cmp     eax, 22h ; '"'
0x18000716f  jz      short loc_1800071B4
0x180007171  cmp     eax, 50h ; 'P'
0x180007174  jnz     short loc_1800071A9
0x180007176  movsxd  rcx, ebp
0x180007179  mov     [r14+rcx*2], r12w
0x18000717e  mov     rcx, [rdi]; bstrString
0x180007181  call    cs:__imp_SysFreeString
0x180007187  mov     [rdi], r14
0x18000718a  mov     ecx, r12d; int
0x18000718d  test    ecx, ecx
0x18000718f  js      short loc_1800071A3
0x180007191  mov     rax, rdi
0x180007194  add     rsp, 20h
0x180007198  pop     r15
0x18000719a  pop     r14
0x18000719c  pop     r12
0x18000719e  pop     rdi
0x18000719f  pop     rsi
0x1800071a0  pop     rbp
0x1800071a1  pop     rbx
0x1800071a2  retn
0x1800071a3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800071a9  mov     ecx, 80004005h; int
0x1800071ae  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800071b4  mov     ecx, 80070057h; int
0x1800071b9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800071bf  mov     ecx, 8007000Eh; int
0x1800071c4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
