# CXMLReader::ReduceStack(CParseNode *)

- ea: `0x18002783c`
- end: `0x1800278b2`
- name: `?ReduceStack@CXMLReader@@AEAAXPEAVCParseNode@@@Z`
- size: `118`
- prototype: `void __fastcall(CXMLReader *__hidden this, struct CParseNode *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800232e4`
- `0x180025654`
- `0x180027944`

## callees

- `0x180025f98`
- `0x1800266bc`
- `0x18002783c`

## pseudocode

```c
void __fastcall CXMLReader::ReduceStack(CXMLReader *this, struct CParseNode *a2)
{
  CNodeStack *v3; // rsi
  __int64 v5; // rcx
  __int64 v7; // rax
  CParseNode *v8; // rax
  struct CParseNode *v9; // rbx

  v3 = (CXMLReader *)((char *)this + 416);
  do
  {
    v8 = (CParseNode *)CNodeStack::Pop(v3);
    v9 = v8;
    if ( !v8 )
      break;
    CParseNode::Init(v8, 0, 0, 0, 0, 0);
    v5 = *((_QWORD *)this + 51);
    if ( (*(_DWORD *)(v5 + 20))-- == 1 )
    {
      v7 = *(_QWORD *)(v5 + 8);
      if ( v7 )
        continue;
    }
    v7 = v5;
    *((_QWORD *)this + 51) = v7;
  }
  while ( v9 != a2 );
}

```

## disassembly

```asm
0x18002783c  push    rbx
0x18002783e  push    rbp
0x18002783f  push    rsi
0x180027840  push    rdi
0x180027841  sub     rsp, 38h
0x180027845  mov     rbp, rdx
0x180027848  lea     rsi, [rcx+1A0h]
0x18002784f  mov     rdi, rcx
0x180027852  jmp     short loc_180027899
0x180027854  mov     [rsp+58h+var_30], 0; unsigned int
0x18002785c  xor     r9d, r9d; unsigned __int16 *
0x18002785f  xor     r8d, r8d; unsigned int
0x180027862  mov     [rsp+58h+var_38], 0; unsigned int
0x18002786a  xor     edx, edx; struct CParseNode *
0x18002786c  mov     rcx, rbx; this
0x18002786f  call    ?Init@CParseNode@@QEAAJPEAV1@KPEBGKK@Z; CParseNode::Init(CParseNode *,ulong,ushort const *,ulong,ulong)
0x180027874  mov     rcx, [rdi+198h]
0x18002787b  add     dword ptr [rcx+14h], 0FFFFFFFFh
0x18002787f  jnz     short loc_18002788A
0x180027881  mov     rax, [rcx+8]
0x180027885  test    rax, rax
0x180027888  jnz     short loc_18002788D
0x18002788a  mov     rax, rcx
0x18002788d  mov     [rdi+198h], rax
0x180027894  cmp     rbx, rbp
0x180027897  jz      short loc_1800278A9
0x180027899  mov     rcx, rsi; this
0x18002789c  call    ?Pop@CNodeStack@@QEAAPEAXXZ; CNodeStack::Pop(void)
0x1800278a1  mov     rbx, rax
0x1800278a4  test    rax, rax
0x1800278a7  jnz     short loc_180027854
0x1800278a9  add     rsp, 38h
0x1800278ad  pop     rdi
0x1800278ae  pop     rsi
0x1800278af  pop     rbp
0x1800278b0  pop     rbx
0x1800278b1  retn
```
