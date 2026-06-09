# Token::Accept(XPathQueryStringCompiler *)

- ea: `0x18000f5c0`
- end: `0x18000f5fd`
- name: `?Accept@Token@@UEAAJPEAVXPathQueryStringCompiler@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(Token *__hidden this, struct XPathQueryStringCompiler *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008ef0`
- `0x18000f5c0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Token::Accept(Token *this, struct XPathQueryStringCompiler *a2)
{
  unsigned int i; // r8d

  for ( i = 0; i < 6; ++i )
  {
    if ( *((_DWORD *)this + 7) == LODWORD(qword_1800192A0[2 * i]) )
      return (*(&funcs_18000F5F2 + 2 * i))(a2, this);
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18000f5c0  mov     r10, rdx
0x18000f5c3  lea     r11, qword_1800192A0
0x18000f5ca  xor     r8d, r8d
0x18000f5cd  cmp     r8d, 6
0x18000f5d1  jnb     short loc_18000F5F7
0x18000f5d3  mov     r9d, r8d
0x18000f5d6  add     r9, r9
0x18000f5d9  mov     eax, [r11+r9*8]
0x18000f5dd  cmp     [rcx+1Ch], eax
0x18000f5e0  jz      short loc_18000F5E7
0x18000f5e2  inc     r8d
0x18000f5e5  jmp     short loc_18000F5CD
0x18000f5e7  mov     rax, (funcs_18000F5F2 - 1800192A0h)[r11+r9*8]
0x18000f5ec  mov     rdx, rcx
0x18000f5ef  mov     rcx, r10
0x18000f5f2  jmp     _guard_dispatch_icall$thunk$10345483385596137414; XPathQueryStringCompiler::ProcessDoubleSlashToken(Token *) ...
0x18000f5f7  mov     eax, 8000FFFFh
0x18000f5fc  retn
```
