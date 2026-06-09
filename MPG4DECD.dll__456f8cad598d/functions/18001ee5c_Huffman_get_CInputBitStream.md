# Huffman::get(CInputBitStream *)

- ea: `0x18001ee5c`
- end: `0x18001ef62`
- name: `?get@Huffman@@QEAAJPEAVCInputBitStream@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(Huffman *this, struct CInputBitStream *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c330`
- `0x18000c5b0`
- `0x18000c9c0`
- `0x18000cd98`
- `0x18000cf1c`
- `0x18000d300`
- `0x18000db00`
- `0x18000e040`
- `0x18000e4d0`
- `0x1800129f8`

## callees

- `0x18001edb0`
- `0x18001ee5c`

## pseudocode

```c
__int64 __fastcall Huffman::get(Huffman *this, struct CInputBitStream *a2)
{
  __int64 v2; // rsi
  int i; // edx
  unsigned int v6; // r9d
  __int64 v7; // r11
  __int64 v8; // r10
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  char v12; // cl
  __int64 v13; // rdi
  signed int v14; // edx

  v2 = *((_QWORD *)this + 4);
  for ( i = 0; ; v2 = *(_QWORD *)(*((_QWORD *)this + 5) + 16LL * i + 8) )
  {
    v6 = *((_DWORD *)a2 + 4);
    v7 = 2LL * i;
    v8 = *(unsigned int *)(*((_QWORD *)this + 5) + 16LL * i);
    if ( (unsigned int)v8 <= v6 )
    {
      _mm_lfence();
      v9 = *((_DWORD *)a2 + 3) >> (v6 - v8);
LABEL_4:
      v10 = *((_DWORD *)&getMask + v8) & v9;
      goto LABEL_13;
    }
    v11 = *((_DWORD *)a2 + 3);
    if ( *((int *)a2 + 2) >= 2 )
    {
      v11 = *(unsigned __int8 *)(*(_QWORD *)a2 + 1LL) | ((**(unsigned __int8 **)a2 | (v11 << 8)) << 8);
      v12 = v6 - v8 + 16;
LABEL_7:
      v9 = v11 >> v12;
      goto LABEL_4;
    }
    if ( *((_DWORD *)a2 + 2) )
    {
      v11 = **(unsigned __int8 **)a2 | (v11 << 8);
      v6 += 8;
    }
    _mm_lfence();
    if ( v6 >= (unsigned int)v8 )
    {
      v12 = v6 - v8;
      goto LABEL_7;
    }
    v10 = (*((_DWORD *)&getMask + v6) & v11) << (v8 - v6);
LABEL_13:
    v13 = v10;
    v14 = *(_DWORD *)(v2 + 8LL * v10 + 4);
    if ( v14 > 0 )
      break;
    if ( v14 )
    {
      *((_DWORD *)a2 + 5) = 3;
      return 0;
    }
    CInputBitStream::flushBitsInline(a2, *(_DWORD *)(*((_QWORD *)this + 5) + 8 * v7));
    i = *(_DWORD *)(v2 + 8 * v13);
  }
  CInputBitStream::flushBitsInline(a2, v14);
  return *(unsigned int *)(v2 + 8 * v13);
}

```

## disassembly

```asm
0x18001ee5c  push    rbx
0x18001ee5e  push    rbp
0x18001ee5f  push    rsi
0x18001ee60  push    rdi
0x18001ee61  push    r14
0x18001ee63  sub     rsp, 20h
0x18001ee67  mov     rsi, [rcx+20h]
0x18001ee6b  lea     r14, ?getMask@@3PAKA; ulong near * getMask
0x18001ee72  mov     rbx, rdx
0x18001ee75  mov     rbp, rcx
0x18001ee78  xor     edx, edx
0x18001ee7a  mov     rax, [rbp+28h]
0x18001ee7e  mov     r9d, [rbx+10h]
0x18001ee82  movsxd  r11, edx
0x18001ee85  add     r11, r11
0x18001ee88  mov     r10d, [rax+r11*8]
0x18001ee8c  cmp     r10d, r9d
0x18001ee8f  ja      short loc_18001EEA7
0x18001ee91  lfence
0x18001ee94  mov     r8d, [rbx+0Ch]
0x18001ee98  sub     r9d, r10d
0x18001ee9b  mov     cl, r9b
0x18001ee9e  shr     r8d, cl
0x18001eea1  and     r8d, [r14+r10*4]
0x18001eea5  jmp     short loc_18001EF0C
0x18001eea7  cmp     dword ptr [rbx+8], 2
0x18001eeab  mov     r8d, [rbx+0Ch]
0x18001eeaf  jl      short loc_18001EED5
0x18001eeb1  mov     rdx, [rbx]
0x18001eeb4  shl     r8d, 8
0x18001eeb8  movzx   eax, byte ptr [rdx]
0x18001eebb  or      r8d, eax
0x18001eebe  movzx   eax, byte ptr [rdx+1]
0x18001eec2  shl     r8d, 8
0x18001eec6  or      r8d, eax
0x18001eec9  sub     r9d, r10d
0x18001eecc  lea     ecx, [r9+10h]
0x18001eed0  sar     r8d, cl
0x18001eed3  jmp     short loc_18001EEA1
0x18001eed5  cmp     dword ptr [rbx+8], 0
0x18001eed9  jz      short loc_18001EEEC
0x18001eedb  mov     rax, [rbx]
0x18001eede  shl     r8d, 8
0x18001eee2  movzx   ecx, byte ptr [rax]
0x18001eee5  or      r8d, ecx
0x18001eee8  add     r9d, 8
0x18001eeec  lfence
0x18001eeef  cmp     r9d, r10d
0x18001eef2  jb      short loc_18001EEFC
0x18001eef4  sub     r9d, r10d
0x18001eef7  mov     cl, r9b
0x18001eefa  jmp     short loc_18001EED0
0x18001eefc  sub     r10d, r9d
0x18001eeff  mov     eax, r9d
0x18001ef02  mov     cl, r10b
0x18001ef05  and     r8d, [r14+rax*4]
0x18001ef09  shl     r8d, cl
0x18001ef0c  movsxd  rdi, r8d
0x18001ef0f  mov     edx, [rsi+rdi*8+4]; unsigned int
0x18001ef13  test    edx, edx
0x18001ef15  jg      short loc_18001EF4C
0x18001ef17  jnz     short loc_18001EF41
0x18001ef19  mov     rdx, [rbp+28h]
0x18001ef1d  mov     rcx, rbx; this
0x18001ef20  mov     edx, [rdx+r11*8]; unsigned int
0x18001ef24  call    ?flushBitsInline@CInputBitStream@@QEAAXK@Z; CInputBitStream::flushBitsInline(ulong)
0x18001ef29  movsxd  rdx, dword ptr [rsi+rdi*8]
0x18001ef2d  mov     rax, [rbp+28h]
0x18001ef31  mov     rcx, rdx
0x18001ef34  add     rcx, rcx
0x18001ef37  mov     rsi, [rax+rcx*8+8]
0x18001ef3c  jmp     loc_18001EE7A
0x18001ef41  mov     dword ptr [rbx+14h], 3
0x18001ef48  xor     eax, eax
0x18001ef4a  jmp     short loc_18001EF57
0x18001ef4c  mov     rcx, rbx; this
0x18001ef4f  call    ?flushBitsInline@CInputBitStream@@QEAAXK@Z; CInputBitStream::flushBitsInline(ulong)
0x18001ef54  mov     eax, [rsi+rdi*8]
0x18001ef57  add     rsp, 20h
0x18001ef5b  pop     r14
0x18001ef5d  pop     rdi
0x18001ef5e  pop     rsi
0x18001ef5f  pop     rbp
0x18001ef60  pop     rbx
0x18001ef61  retn
```
