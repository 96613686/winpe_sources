# CVideoObjectDecoder::checkResyncMarker(void)

- ea: `0x18000dec8`
- end: `0x18000df45`
- name: `?checkResyncMarker@CVideoObjectDecoder@@AEAAJXZ`
- size: `125`
- prototype: `_BOOL8 __fastcall(CVideoObjectDecoder *this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f500`
- `0x18000fa90`
- `0x180010118`
- `0x1800106c0`
- `0x180011040`
- `0x180011aa8`

## callees

- `0x18000dec8`
- `0x18001e81c`

## pseudocode

```c
_BOOL8 __fastcall CVideoObjectDecoder::checkResyncMarker(CVideoObjectDecoder *this)
{
  CInputBitStream *v1; // rsi
  int v3; // edi
  unsigned int v4; // ebx
  int v5; // ebx

  v1 = (CInputBitStream *)*((_QWORD *)this + 274);
  v3 = *((_DWORD *)v1 + 4) & 7;
  v4 = v3;
  if ( !v3 )
    v4 = 8;
  if ( (unsigned int)CInputBitStream::peekBits(v1, v4) != (1 << (v4 - 1)) - 1 )
    return 0;
  if ( !v3 )
    v3 = 8;
  v5 = *((_DWORD *)this + 23) + 16;
  return (*((_DWORD *)&getMask + v5) & (unsigned int)CInputBitStream::peekBits(v1, v5 + v3)) == 1;
}

```

## disassembly

```asm
0x18000dec8  push    rbx
0x18000deca  push    rbp
0x18000decb  push    rsi
0x18000decc  push    rdi
0x18000decd  push    r14
0x18000decf  sub     rsp, 20h
0x18000ded3  mov     rsi, [rcx+890h]
0x18000deda  mov     rbp, rcx
0x18000dedd  mov     r14d, 8
0x18000dee3  mov     rcx, rsi; this
0x18000dee6  mov     edi, [rsi+10h]
0x18000dee9  and     edi, 7
0x18000deec  mov     ebx, edi
0x18000deee  cmovz   ebx, r14d
0x18000def2  mov     edx, ebx; unsigned int
0x18000def4  call    ?peekBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::peekBits(ulong)
0x18000def9  lea     ecx, [rbx-1]
0x18000defc  lea     edx, [r14-7]
0x18000df00  shl     edx, cl
0x18000df02  dec     edx
0x18000df04  cmp     eax, edx
0x18000df06  jnz     short loc_18000DF38
0x18000df08  mov     ebx, [rbp+5Ch]
0x18000df0b  mov     rcx, rsi; this
0x18000df0e  add     ebx, 10h
0x18000df11  test    edi, edi
0x18000df13  cmovz   edi, r14d
0x18000df17  lea     edx, [rbx+rdi]; unsigned int
0x18000df1a  call    ?peekBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::peekBits(ulong)
0x18000df1f  mov     edx, eax
0x18000df21  movsxd  rcx, ebx
0x18000df24  lea     rax, ?getMask@@3PAKA; ulong near * getMask
0x18000df2b  and     edx, [rax+rcx*4]
0x18000df2e  xor     eax, eax
0x18000df30  cmp     edx, 1
0x18000df33  setz    al
0x18000df36  jmp     short loc_18000DF3A
0x18000df38  xor     eax, eax
0x18000df3a  add     rsp, 20h
0x18000df3e  pop     r14
0x18000df40  pop     rdi
0x18000df41  pop     rsi
0x18000df42  pop     rbp
0x18000df43  pop     rbx
0x18000df44  retn
```
