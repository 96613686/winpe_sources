# Huffman::get(CInputBitStream *)

- ea: `0x18001ed9c`
- end: `0x18001eea2`
- name: `?get@Huffman@@QEAAJPEAVCInputBitStream@@@Z`
- size: `262`
- prototype: `int(Huffman *__hidden this, struct CInputBitStream *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c270`
- `0x18000c4f0`
- `0x18000c900`
- `0x18000ccd8`
- `0x18000ce5c`
- `0x18000d240`
- `0x18000da40`
- `0x18000df80`
- `0x18000e410`
- `0x180012938`

## callees

- `0x18001ecf0`
- `0x18001ed9c`

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
0x18001ed9c  push    rbx
0x18001ed9e  push    rbp
0x18001ed9f  push    rsi
0x18001eda0  push    rdi
0x18001eda1  push    r14
0x18001eda3  sub     rsp, 20h
0x18001eda7  mov     rsi, [rcx+20h]
0x18001edab  lea     r14, ?getMask@@3PAKA; ulong near * getMask
0x18001edb2  mov     rbx, rdx
0x18001edb5  mov     rbp, rcx
0x18001edb8  xor     edx, edx
0x18001edba  mov     rax, [rbp+28h]
0x18001edbe  mov     r9d, [rbx+10h]
0x18001edc2  movsxd  r11, edx
0x18001edc5  add     r11, r11
0x18001edc8  mov     r10d, [rax+r11*8]
0x18001edcc  cmp     r10d, r9d
0x18001edcf  ja      short loc_18001EDE7
0x18001edd1  lfence
0x18001edd4  mov     r8d, [rbx+0Ch]
0x18001edd8  sub     r9d, r10d
0x18001eddb  mov     cl, r9b
0x18001edde  shr     r8d, cl
0x18001ede1  and     r8d, [r14+r10*4]
0x18001ede5  jmp     short loc_18001EE4C
0x18001ede7  cmp     dword ptr [rbx+8], 2
0x18001edeb  mov     r8d, [rbx+0Ch]
0x18001edef  jl      short loc_18001EE15
0x18001edf1  mov     rdx, [rbx]
0x18001edf4  shl     r8d, 8
0x18001edf8  movzx   eax, byte ptr [rdx]
0x18001edfb  or      r8d, eax
0x18001edfe  movzx   eax, byte ptr [rdx+1]
0x18001ee02  shl     r8d, 8
0x18001ee06  or      r8d, eax
0x18001ee09  sub     r9d, r10d
0x18001ee0c  lea     ecx, [r9+10h]
0x18001ee10  sar     r8d, cl
0x18001ee13  jmp     short loc_18001EDE1
0x18001ee15  cmp     dword ptr [rbx+8], 0
0x18001ee19  jz      short loc_18001EE2C
0x18001ee1b  mov     rax, [rbx]
0x18001ee1e  shl     r8d, 8
0x18001ee22  movzx   ecx, byte ptr [rax]
0x18001ee25  or      r8d, ecx
0x18001ee28  add     r9d, 8
0x18001ee2c  lfence
0x18001ee2f  cmp     r9d, r10d
0x18001ee32  jb      short loc_18001EE3C
0x18001ee34  sub     r9d, r10d
0x18001ee37  mov     cl, r9b
0x18001ee3a  jmp     short loc_18001EE10
0x18001ee3c  sub     r10d, r9d
0x18001ee3f  mov     eax, r9d
0x18001ee42  mov     cl, r10b
0x18001ee45  and     r8d, [r14+rax*4]
0x18001ee49  shl     r8d, cl
0x18001ee4c  movsxd  rdi, r8d
0x18001ee4f  mov     edx, [rsi+rdi*8+4]; unsigned int
0x18001ee53  test    edx, edx
0x18001ee55  jg      short loc_18001EE8C
0x18001ee57  jnz     short loc_18001EE81
0x18001ee59  mov     rdx, [rbp+28h]
0x18001ee5d  mov     rcx, rbx; this
0x18001ee60  mov     edx, [rdx+r11*8]; unsigned int
0x18001ee64  call    ?flushBitsInline@CInputBitStream@@QEAAXK@Z; CInputBitStream::flushBitsInline(ulong)
0x18001ee69  movsxd  rdx, dword ptr [rsi+rdi*8]
0x18001ee6d  mov     rax, [rbp+28h]
0x18001ee71  mov     rcx, rdx
0x18001ee74  add     rcx, rcx
0x18001ee77  mov     rsi, [rax+rcx*8+8]
0x18001ee7c  jmp     loc_18001EDBA
0x18001ee81  mov     dword ptr [rbx+14h], 3
0x18001ee88  xor     eax, eax
0x18001ee8a  jmp     short loc_18001EE97
0x18001ee8c  mov     rcx, rbx; this
0x18001ee8f  call    ?flushBitsInline@CInputBitStream@@QEAAXK@Z; CInputBitStream::flushBitsInline(ulong)
0x18001ee94  mov     eax, [rsi+rdi*8]
0x18001ee97  add     rsp, 20h
0x18001ee9b  pop     r14
0x18001ee9d  pop     rdi
0x18001ee9e  pop     rsi
0x18001ee9f  pop     rbp
0x18001eea0  pop     rbx
0x18001eea1  retn
```
