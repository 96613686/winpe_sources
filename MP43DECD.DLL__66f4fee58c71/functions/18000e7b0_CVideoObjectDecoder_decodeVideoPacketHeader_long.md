# CVideoObjectDecoder::decodeVideoPacketHeader(long &)

- ea: `0x18000e7b0`
- end: `0x18000e908`
- name: `?decodeVideoPacketHeader@CVideoObjectDecoder@@AEAAJAEAJ@Z`
- size: `344`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *__hidden this, int *)`
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

- `0x18000b0ac`
- `0x18000e7b0`

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
0x18000e7b0  mov     [rsp+arg_0], rbx
0x18000e7b5  mov     [rsp+arg_8], rsi
0x18000e7ba  push    rdi
0x18000e7bb  sub     rsp, 20h
0x18000e7bf  mov     rbx, rcx
0x18000e7c2  mov     rdi, rdx
0x18000e7c5  mov     rcx, [rcx+890h]; this
0x18000e7cc  mov     eax, [rcx+10h]
0x18000e7cf  mov     r8d, eax
0x18000e7d2  and     r8d, 7
0x18000e7d6  jnz     short loc_18000E7E3
0x18000e7d8  lea     edx, [r8+8]; unsigned int
0x18000e7dc  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e7e1  jmp     short loc_18000E7E9
0x18000e7e3  sub     eax, r8d
0x18000e7e6  mov     [rcx+10h], eax
0x18000e7e9  mov     edx, [rbx+5Ch]
0x18000e7ec  mov     rcx, [rbx+890h]; this
0x18000e7f3  add     edx, 10h; unsigned int
0x18000e7f6  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e7fb  mov     ecx, [rbx+74h]
0x18000e7fe  xor     edx, edx
0x18000e800  imul    ecx, [rbx+70h]
0x18000e804  lea     esi, [rdx+1]
0x18000e807  lea     eax, [rcx-1]
0x18000e80a  test    eax, eax
0x18000e80c  jz      short loc_18000E814
0x18000e80e  add     edx, esi; unsigned int
0x18000e810  sar     eax, 1
0x18000e812  jnz     short loc_18000E80E
0x18000e814  xor     eax, eax
0x18000e816  cmp     ecx, esi
0x18000e818  jle     short loc_18000E826
0x18000e81a  mov     rcx, [rbx+890h]; this
0x18000e821  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e826  mov     rcx, [rbx+890h]; this
0x18000e82d  mov     edx, 5; unsigned int
0x18000e832  mov     [rbx+898h], eax
0x18000e838  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e83d  mov     [rdi], eax
0x18000e83f  mov     edx, esi; unsigned int
0x18000e841  mov     rcx, [rbx+890h]; this
0x18000e848  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e84d  mov     rcx, [rbx+890h]
0x18000e854  cmp     dword ptr [rcx+14h], 0
0x18000e858  jnz     loc_18000E8F3
0x18000e85e  test    eax, eax
0x18000e860  jz      short loc_18000E8DE
0x18000e862  jmp     short loc_18000E86E
0x18000e864  cmp     dword ptr [rcx+14h], 0
0x18000e868  jnz     loc_18000E8F3
0x18000e86e  mov     edx, esi; unsigned int
0x18000e870  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e875  mov     rcx, [rbx+890h]; this
0x18000e87c  test    eax, eax
0x18000e87e  jnz     short loc_18000E864
0x18000e880  mov     edx, esi; unsigned int
0x18000e882  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e887  mov     edx, [rbx+0B8h]; unsigned int
0x18000e88d  mov     rcx, [rbx+890h]; this
0x18000e894  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e899  mov     rcx, [rbx+890h]; this
0x18000e8a0  mov     edx, esi; unsigned int
0x18000e8a2  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e8a7  mov     rcx, [rbx+890h]; this
0x18000e8ae  mov     edx, 2; unsigned int
0x18000e8b3  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e8b8  mov     rcx, [rbx+890h]; this
0x18000e8bf  mov     edi, 3
0x18000e8c4  mov     edx, edi; unsigned int
0x18000e8c6  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e8cb  cmp     [rbx+58h], esi
0x18000e8ce  jnz     short loc_18000E8DE
0x18000e8d0  mov     rcx, [rbx+890h]; this
0x18000e8d7  mov     edx, edi; unsigned int
0x18000e8d9  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e8de  mov     rax, [rbx+890h]
0x18000e8e5  mov     ecx, [rax+14h]
0x18000e8e8  neg     ecx
0x18000e8ea  sbb     eax, eax
0x18000e8ec  and     eax, 0FFFFFF9Bh
0x18000e8ef  add     eax, esi
0x18000e8f1  jmp     short loc_18000E8F8
0x18000e8f3  mov     eax, 0FFFFFF9Ch
0x18000e8f8  mov     rbx, [rsp+28h+arg_0]
0x18000e8fd  mov     rsi, [rsp+28h+arg_8]
0x18000e902  add     rsp, 20h
0x18000e906  pop     rdi
0x18000e907  retn
```
