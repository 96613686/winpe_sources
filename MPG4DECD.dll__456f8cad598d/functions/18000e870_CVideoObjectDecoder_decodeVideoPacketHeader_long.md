# CVideoObjectDecoder::decodeVideoPacketHeader(long &)

- ea: `0x18000e870`
- end: `0x18000e9c8`
- name: `?decodeVideoPacketHeader@CVideoObjectDecoder@@AEAAJAEAJ@Z`
- size: `344`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *__hidden this, int *)`
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

- `0x18000b16c`
- `0x18000e870`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::decodeVideoPacketHeader(CVideoObjectDecoder *this, int *a2)
{
  CInputBitStream *v4; // rcx
  unsigned int v5; // edx
  int v6; // ecx
  int v7; // eax
  unsigned int Bits; // eax
  CInputBitStream *v9; // rcx
  unsigned int v10; // eax
  CInputBitStream *v11; // rcx
  unsigned int v12; // eax

  v4 = (CInputBitStream *)*((_QWORD *)this + 274);
  if ( (*((_DWORD *)v4 + 4) & 7) != 0 )
    *((_DWORD *)v4 + 4) -= *((_DWORD *)v4 + 4) & 7;
  else
    CInputBitStream::getBits(v4, 8u);
  CInputBitStream::getBits(*((CInputBitStream **)this + 274), *((_DWORD *)this + 23) + 16);
  v5 = 0;
  v6 = *((_DWORD *)this + 28) * *((_DWORD *)this + 29);
  v7 = v6 - 1;
  if ( v6 != 1 )
  {
    do
    {
      ++v5;
      v7 >>= 1;
    }
    while ( v7 );
  }
  Bits = 0;
  if ( v6 > 1 )
    Bits = CInputBitStream::getBits(*((CInputBitStream **)this + 274), v5);
  v9 = (CInputBitStream *)*((_QWORD *)this + 274);
  *((_DWORD *)this + 550) = Bits;
  *a2 = CInputBitStream::getBits(v9, 5u);
  v10 = CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u);
  v11 = (CInputBitStream *)*((_QWORD *)this + 274);
  if ( *((_DWORD *)v11 + 5) )
    return 4294967196LL;
  if ( v10 )
  {
    while ( 1 )
    {
      v12 = CInputBitStream::getBits(v11, 1u);
      v11 = (CInputBitStream *)*((_QWORD *)this + 274);
      if ( !v12 )
        break;
      if ( *((_DWORD *)v11 + 5) )
        return 4294967196LL;
    }
    CInputBitStream::getBits(v11, 1u);
    CInputBitStream::getBits(*((CInputBitStream **)this + 274), *((_DWORD *)this + 46));
    CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u);
    CInputBitStream::getBits(*((CInputBitStream **)this + 274), 2u);
    CInputBitStream::getBits(*((CInputBitStream **)this + 274), 3u);
    if ( *((_DWORD *)this + 22) == 1 )
      CInputBitStream::getBits(*((CInputBitStream **)this + 274), 3u);
  }
  return *(_DWORD *)(*((_QWORD *)this + 274) + 20LL) != 0 ? -100 : 1;
}

```

## disassembly

```asm
0x18000e870  mov     [rsp+arg_0], rbx
0x18000e875  mov     [rsp+arg_8], rsi
0x18000e87a  push    rdi
0x18000e87b  sub     rsp, 20h
0x18000e87f  mov     rbx, rcx
0x18000e882  mov     rdi, rdx
0x18000e885  mov     rcx, [rcx+890h]; this
0x18000e88c  mov     eax, [rcx+10h]
0x18000e88f  mov     r8d, eax
0x18000e892  and     r8d, 7
0x18000e896  jnz     short loc_18000E8A3
0x18000e898  lea     edx, [r8+8]; unsigned int
0x18000e89c  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e8a1  jmp     short loc_18000E8A9
0x18000e8a3  sub     eax, r8d
0x18000e8a6  mov     [rcx+10h], eax
0x18000e8a9  mov     edx, [rbx+5Ch]
0x18000e8ac  mov     rcx, [rbx+890h]; this
0x18000e8b3  add     edx, 10h; unsigned int
0x18000e8b6  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e8bb  mov     ecx, [rbx+74h]
0x18000e8be  xor     edx, edx
0x18000e8c0  imul    ecx, [rbx+70h]
0x18000e8c4  lea     esi, [rdx+1]
0x18000e8c7  lea     eax, [rcx-1]
0x18000e8ca  test    eax, eax
0x18000e8cc  jz      short loc_18000E8D4
0x18000e8ce  add     edx, esi; unsigned int
0x18000e8d0  sar     eax, 1
0x18000e8d2  jnz     short loc_18000E8CE
0x18000e8d4  xor     eax, eax
0x18000e8d6  cmp     ecx, esi
0x18000e8d8  jle     short loc_18000E8E6
0x18000e8da  mov     rcx, [rbx+890h]; this
0x18000e8e1  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e8e6  mov     rcx, [rbx+890h]; this
0x18000e8ed  mov     edx, 5; unsigned int
0x18000e8f2  mov     [rbx+898h], eax
0x18000e8f8  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e8fd  mov     [rdi], eax
0x18000e8ff  mov     edx, esi; unsigned int
0x18000e901  mov     rcx, [rbx+890h]; this
0x18000e908  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e90d  mov     rcx, [rbx+890h]
0x18000e914  cmp     dword ptr [rcx+14h], 0
0x18000e918  jnz     loc_18000E9B3
0x18000e91e  test    eax, eax
0x18000e920  jz      short loc_18000E99E
0x18000e922  jmp     short loc_18000E92E
0x18000e924  cmp     dword ptr [rcx+14h], 0
0x18000e928  jnz     loc_18000E9B3
0x18000e92e  mov     edx, esi; unsigned int
0x18000e930  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e935  mov     rcx, [rbx+890h]; this
0x18000e93c  test    eax, eax
0x18000e93e  jnz     short loc_18000E924
0x18000e940  mov     edx, esi; unsigned int
0x18000e942  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e947  mov     edx, [rbx+0B8h]; unsigned int
0x18000e94d  mov     rcx, [rbx+890h]; this
0x18000e954  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e959  mov     rcx, [rbx+890h]; this
0x18000e960  mov     edx, esi; unsigned int
0x18000e962  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e967  mov     rcx, [rbx+890h]; this
0x18000e96e  mov     edx, 2; unsigned int
0x18000e973  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e978  mov     rcx, [rbx+890h]; this
0x18000e97f  mov     edi, 3
0x18000e984  mov     edx, edi; unsigned int
0x18000e986  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e98b  cmp     [rbx+58h], esi
0x18000e98e  jnz     short loc_18000E99E
0x18000e990  mov     rcx, [rbx+890h]; this
0x18000e997  mov     edx, edi; unsigned int
0x18000e999  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e99e  mov     rax, [rbx+890h]
0x18000e9a5  mov     ecx, [rax+14h]
0x18000e9a8  neg     ecx
0x18000e9aa  sbb     eax, eax
0x18000e9ac  and     eax, 0FFFFFF9Bh
0x18000e9af  add     eax, esi
0x18000e9b1  jmp     short loc_18000E9B8
0x18000e9b3  mov     eax, 0FFFFFF9Ch
0x18000e9b8  mov     rbx, [rsp+28h+arg_0]
0x18000e9bd  mov     rsi, [rsp+28h+arg_8]
0x18000e9c2  add     rsp, 20h
0x18000e9c6  pop     rdi
0x18000e9c7  retn
```
