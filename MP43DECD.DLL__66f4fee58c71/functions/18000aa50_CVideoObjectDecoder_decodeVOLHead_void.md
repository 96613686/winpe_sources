# CVideoObjectDecoder::decodeVOLHead(void)

- ea: `0x18000aa50`
- end: `0x18000ad2f`
- name: `?decodeVOLHead@CVideoObjectDecoder@@QEAAJXZ`
- size: `735`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004ffc`
- `0x180007800`

## callees

- `0x18000aa50`
- `0x18000b0ac`
- `0x18000b198`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::decodeVOLHead(CVideoObjectDecoder *this)
{
  int Bits; // eax
  int v3; // ecx
  CInputBitStream *v4; // rcx
  CInputBitStream *v5; // rcx

  *((_DWORD *)this + 935) = 0;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 0x18u) != 1 )
    return 4294967196LL;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 3u) )
    return 4294967196LL;
  CInputBitStream::getBits(*((CInputBitStream **)this + 274), 5u);
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 0x18u) != 1 )
    return 4294967196LL;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 4u) != 2 )
    return 4294967196LL;
  CInputBitStream::getBits(*((CInputBitStream **)this + 274), 4u);
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) )
    return 4294967196LL;
  CInputBitStream::getBits(*((CInputBitStream **)this + 274), 8u);
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) )
    return 4294967196LL;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 4u) != 1 )
    return 4294967196LL;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) )
    return 4294967196LL;
  CInputBitStream::getBits(*((CInputBitStream **)this + 274), 2u);
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) != 1 )
    return 4294967196LL;
  Bits = CInputBitStream::getBits(*((CInputBitStream **)this + 274), 0x10u);
  *((_DWORD *)this + 13) = Bits;
  v3 = 1;
  *((_DWORD *)this + 46) = 1;
  do
  {
    if ( Bits == 1 )
      break;
    Bits >>= 1;
    *((_DWORD *)this + 46) = ++v3;
  }
  while ( v3 <= 15 );
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) != 1 )
    return 4294967196LL;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) )
    return 4294967196LL;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) != 1 )
    return 4294967196LL;
  if ( (int)CInputBitStream::getBits(*((CInputBitStream **)this + 274), 0xDu) < 1 )
    return 4294967196LL;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) != 1 )
    return 4294967196LL;
  if ( (int)CInputBitStream::getBits(*((CInputBitStream **)this + 274), 0xDu) < 1 )
    return 4294967196LL;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) != 1 )
    return 4294967196LL;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) )
    return 4294967196LL;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) != 1 )
    return 4294967196LL;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) )
    return 4294967196LL;
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) )
    return 4294967196LL;
  v4 = (CInputBitStream *)*((_QWORD *)this + 274);
  *((_DWORD *)this + 14) = 5;
  CInputBitStream::getBits(v4, 1u);
  if ( !CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) )
    return 4294967196LL;
  CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u);
  if ( CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) == 1
    || CInputBitStream::getBits(*((CInputBitStream **)this + 274), 1u) )
  {
    return 4294967196LL;
  }
  v5 = (CInputBitStream *)*((_QWORD *)this + 274);
  if ( (*((_DWORD *)v5 + 4) & 7) != 0 )
    *((_DWORD *)v5 + 4) -= *((_DWORD *)v5 + 4) & 7;
  else
    CInputBitStream::getBits(v5, 0);
  CVideoObjectDecoder::setSliceCode(this, 0);
  return 0;
}

```

## disassembly

```asm
0x18000aa50  mov     [rsp+arg_0], rbx
0x18000aa55  push    rdi
0x18000aa56  sub     rsp, 20h
0x18000aa5a  mov     rbx, rcx
0x18000aa5d  mov     dword ptr [rcx+0E9Ch], 0
0x18000aa67  mov     rcx, [rcx+890h]; this
0x18000aa6e  mov     edx, 18h; unsigned int
0x18000aa73  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000aa78  mov     edi, 1
0x18000aa7d  cmp     eax, edi
0x18000aa7f  jnz     loc_18000AD1F
0x18000aa85  mov     rcx, [rbx+890h]; this
0x18000aa8c  lea     edx, [rdi+2]; unsigned int
0x18000aa8f  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000aa94  test    eax, eax
0x18000aa96  jnz     loc_18000AD1F
0x18000aa9c  mov     rcx, [rbx+890h]; this
0x18000aaa3  lea     edx, [rdi+4]; unsigned int
0x18000aaa6  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000aaab  mov     rcx, [rbx+890h]; this
0x18000aab2  lea     edx, [rdi+17h]; unsigned int
0x18000aab5  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000aaba  cmp     eax, edi
0x18000aabc  jnz     loc_18000AD1F
0x18000aac2  mov     rcx, [rbx+890h]; this
0x18000aac9  lea     edx, [rdi+3]; unsigned int
0x18000aacc  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000aad1  cmp     eax, 2
0x18000aad4  jnz     loc_18000AD1F
0x18000aada  mov     rcx, [rbx+890h]; this
0x18000aae1  lea     edx, [rdi+3]; unsigned int
0x18000aae4  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000aae9  mov     rcx, [rbx+890h]; this
0x18000aaf0  mov     edx, edi; unsigned int
0x18000aaf2  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000aaf7  test    eax, eax
0x18000aaf9  jnz     loc_18000AD1F
0x18000aaff  mov     rcx, [rbx+890h]; this
0x18000ab06  lea     edx, [rdi+7]; unsigned int
0x18000ab09  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ab0e  mov     rcx, [rbx+890h]; this
0x18000ab15  mov     edx, edi; unsigned int
0x18000ab17  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ab1c  test    eax, eax
0x18000ab1e  jnz     loc_18000AD1F
0x18000ab24  mov     rcx, [rbx+890h]; this
0x18000ab2b  lea     edx, [rdi+3]; unsigned int
0x18000ab2e  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ab33  cmp     eax, edi
0x18000ab35  jnz     loc_18000AD1F
0x18000ab3b  mov     rcx, [rbx+890h]; this
0x18000ab42  mov     edx, edi; unsigned int
0x18000ab44  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ab49  test    eax, eax
0x18000ab4b  jnz     loc_18000AD1F
0x18000ab51  mov     rcx, [rbx+890h]; this
0x18000ab58  lea     edx, [rdi+1]; unsigned int
0x18000ab5b  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ab60  mov     rcx, [rbx+890h]; this
0x18000ab67  mov     edx, edi; unsigned int
0x18000ab69  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ab6e  cmp     eax, edi
0x18000ab70  jnz     loc_18000AD1F
0x18000ab76  mov     rcx, [rbx+890h]; this
0x18000ab7d  lea     edx, [rdi+0Fh]; unsigned int
0x18000ab80  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ab85  mov     [rbx+34h], eax
0x18000ab88  mov     ecx, edi
0x18000ab8a  mov     [rbx+0B8h], edi
0x18000ab90  cmp     eax, edi
0x18000ab92  jz      short loc_18000ABA3
0x18000ab94  sar     eax, 1
0x18000ab96  inc     ecx
0x18000ab98  mov     [rbx+0B8h], ecx
0x18000ab9e  cmp     ecx, 0Fh
0x18000aba1  jle     short loc_18000AB90
0x18000aba3  mov     rcx, [rbx+890h]; this
0x18000abaa  mov     edx, edi; unsigned int
0x18000abac  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000abb1  cmp     eax, edi
0x18000abb3  jnz     loc_18000AD1F
0x18000abb9  mov     rcx, [rbx+890h]; this
0x18000abc0  mov     edx, edi; unsigned int
0x18000abc2  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000abc7  test    eax, eax
0x18000abc9  jnz     loc_18000AD1F
0x18000abcf  mov     rcx, [rbx+890h]; this
0x18000abd6  mov     edx, edi; unsigned int
0x18000abd8  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000abdd  cmp     eax, edi
0x18000abdf  jnz     loc_18000AD1F
0x18000abe5  mov     rcx, [rbx+890h]; this
0x18000abec  mov     edx, 0Dh; unsigned int
0x18000abf1  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000abf6  cmp     eax, edi
0x18000abf8  jl      loc_18000AD1F
0x18000abfe  mov     rcx, [rbx+890h]; this
0x18000ac05  mov     edx, edi; unsigned int
0x18000ac07  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac0c  cmp     eax, edi
0x18000ac0e  jnz     loc_18000AD1F
0x18000ac14  mov     rcx, [rbx+890h]; this
0x18000ac1b  mov     edx, 0Dh; unsigned int
0x18000ac20  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac25  cmp     eax, edi
0x18000ac27  jl      loc_18000AD1F
0x18000ac2d  mov     rcx, [rbx+890h]; this
0x18000ac34  mov     edx, edi; unsigned int
0x18000ac36  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac3b  cmp     eax, edi
0x18000ac3d  jnz     loc_18000AD1F
0x18000ac43  mov     rcx, [rbx+890h]; this
0x18000ac4a  mov     edx, edi; unsigned int
0x18000ac4c  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac51  test    eax, eax
0x18000ac53  jnz     loc_18000AD1F
0x18000ac59  mov     rcx, [rbx+890h]; this
0x18000ac60  mov     edx, edi; unsigned int
0x18000ac62  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac67  cmp     eax, edi
0x18000ac69  jnz     loc_18000AD1F
0x18000ac6f  mov     rcx, [rbx+890h]; this
0x18000ac76  mov     edx, edi; unsigned int
0x18000ac78  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac7d  test    eax, eax
0x18000ac7f  jnz     loc_18000AD1F
0x18000ac85  mov     rcx, [rbx+890h]; this
0x18000ac8c  mov     edx, edi; unsigned int
0x18000ac8e  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac93  test    eax, eax
0x18000ac95  jnz     loc_18000AD1F
0x18000ac9b  mov     rcx, [rbx+890h]; this
0x18000aca2  mov     edx, edi; unsigned int
0x18000aca4  mov     dword ptr [rbx+38h], 5
0x18000acab  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000acb0  mov     rcx, [rbx+890h]; this
0x18000acb7  mov     edx, edi; unsigned int
0x18000acb9  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000acbe  test    eax, eax
0x18000acc0  jz      short loc_18000AD1F
0x18000acc2  mov     rcx, [rbx+890h]; this
0x18000acc9  mov     edx, edi; unsigned int
0x18000accb  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000acd0  mov     rcx, [rbx+890h]; this
0x18000acd7  mov     edx, edi; unsigned int
0x18000acd9  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000acde  cmp     eax, edi
0x18000ace0  jz      short loc_18000AD1F
0x18000ace2  mov     rcx, [rbx+890h]; this
0x18000ace9  mov     edx, edi; unsigned int
0x18000aceb  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000acf0  test    eax, eax
0x18000acf2  jnz     short loc_18000AD1F
0x18000acf4  mov     rcx, [rbx+890h]; this
0x18000acfb  mov     eax, [rcx+10h]
0x18000acfe  mov     edx, eax
0x18000ad00  and     edx, 7; unsigned int
0x18000ad03  jnz     short loc_18000AD0C
0x18000ad05  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ad0a  jmp     short loc_18000AD11
0x18000ad0c  sub     eax, edx
0x18000ad0e  mov     [rcx+10h], eax
0x18000ad11  xor     edx, edx; int
0x18000ad13  mov     rcx, rbx; this
0x18000ad16  call    ?setSliceCode@CVideoObjectDecoder@@AEAAJJ@Z; CVideoObjectDecoder::setSliceCode(long)
0x18000ad1b  xor     eax, eax
0x18000ad1d  jmp     short loc_18000AD24
0x18000ad1f  mov     eax, 0FFFFFF9Ch
0x18000ad24  mov     rbx, [rsp+28h+arg_0]
0x18000ad29  add     rsp, 20h
0x18000ad2d  pop     rdi
0x18000ad2e  retn
```
