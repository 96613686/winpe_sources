# CVideoObjectDecoder::checkResyncMarker(void)

- ea: `0x18000de08`
- end: `0x18000de85`
- name: `?checkResyncMarker@CVideoObjectDecoder@@AEAAJXZ`
- size: `125`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f440`
- `0x18000f9d0`
- `0x180010058`
- `0x180010600`
- `0x180010f80`
- `0x1800119e8`

## callees

- `0x18000de08`
- `0x18001e75c`

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
  if ( CInputBitStream::peekBits(v1, v4) != (1 << (v4 - 1)) - 1 )
    return 0;
  if ( !v3 )
    v3 = 8;
  v5 = *((_DWORD *)this + 23) + 16;
  return (*((_DWORD *)&getMask + v5) & CInputBitStream::peekBits(v1, v5 + v3)) == 1;
}

```

## disassembly

```asm
0x18000de08  push    rbx
0x18000de0a  push    rbp
0x18000de0b  push    rsi
0x18000de0c  push    rdi
0x18000de0d  push    r14
0x18000de0f  sub     rsp, 20h
0x18000de13  mov     rsi, [rcx+890h]
0x18000de1a  mov     rbp, rcx
0x18000de1d  mov     r14d, 8
0x18000de23  mov     rcx, rsi; this
0x18000de26  mov     edi, [rsi+10h]
0x18000de29  and     edi, 7
0x18000de2c  mov     ebx, edi
0x18000de2e  cmovz   ebx, r14d
0x18000de32  mov     edx, ebx; unsigned int
0x18000de34  call    ?peekBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::peekBits(ulong)
0x18000de39  lea     ecx, [rbx-1]
0x18000de3c  lea     edx, [r14-7]
0x18000de40  shl     edx, cl
0x18000de42  dec     edx
0x18000de44  cmp     eax, edx
0x18000de46  jnz     short loc_18000DE78
0x18000de48  mov     ebx, [rbp+5Ch]
0x18000de4b  mov     rcx, rsi; this
0x18000de4e  add     ebx, 10h
0x18000de51  test    edi, edi
0x18000de53  cmovz   edi, r14d
0x18000de57  lea     edx, [rbx+rdi]; unsigned int
0x18000de5a  call    ?peekBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::peekBits(ulong)
0x18000de5f  mov     edx, eax
0x18000de61  movsxd  rcx, ebx
0x18000de64  lea     rax, ?getMask@@3PAKA; ulong near * getMask
0x18000de6b  and     edx, [rax+rcx*4]
0x18000de6e  xor     eax, eax
0x18000de70  cmp     edx, 1
0x18000de73  setz    al
0x18000de76  jmp     short loc_18000DE7A
0x18000de78  xor     eax, eax
0x18000de7a  add     rsp, 20h
0x18000de7e  pop     r14
0x18000de80  pop     rdi
0x18000de81  pop     rsi
0x18000de82  pop     rbp
0x18000de83  pop     rbx
0x18000de84  retn
```
