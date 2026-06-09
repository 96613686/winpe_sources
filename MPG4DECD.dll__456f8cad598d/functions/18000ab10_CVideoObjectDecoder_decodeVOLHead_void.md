# CVideoObjectDecoder::decodeVOLHead(void)

- ea: `0x18000ab10`
- end: `0x18000adef`
- name: `?decodeVOLHead@CVideoObjectDecoder@@QEAAJXZ`
- size: `735`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800050bc`
- `0x1800078c0`

## callees

- `0x18000ab10`
- `0x18000b16c`
- `0x18000b258`

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
0x18000ab10  mov     [rsp+arg_0], rbx
0x18000ab15  push    rdi
0x18000ab16  sub     rsp, 20h
0x18000ab1a  mov     rbx, rcx
0x18000ab1d  mov     dword ptr [rcx+0E9Ch], 0
0x18000ab27  mov     rcx, [rcx+890h]; this
0x18000ab2e  mov     edx, 18h; unsigned int
0x18000ab33  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ab38  mov     edi, 1
0x18000ab3d  cmp     eax, edi
0x18000ab3f  jnz     loc_18000ADDF
0x18000ab45  mov     rcx, [rbx+890h]; this
0x18000ab4c  lea     edx, [rdi+2]; unsigned int
0x18000ab4f  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ab54  test    eax, eax
0x18000ab56  jnz     loc_18000ADDF
0x18000ab5c  mov     rcx, [rbx+890h]; this
0x18000ab63  lea     edx, [rdi+4]; unsigned int
0x18000ab66  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ab6b  mov     rcx, [rbx+890h]; this
0x18000ab72  lea     edx, [rdi+17h]; unsigned int
0x18000ab75  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ab7a  cmp     eax, edi
0x18000ab7c  jnz     loc_18000ADDF
0x18000ab82  mov     rcx, [rbx+890h]; this
0x18000ab89  lea     edx, [rdi+3]; unsigned int
0x18000ab8c  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ab91  cmp     eax, 2
0x18000ab94  jnz     loc_18000ADDF
0x18000ab9a  mov     rcx, [rbx+890h]; this
0x18000aba1  lea     edx, [rdi+3]; unsigned int
0x18000aba4  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000aba9  mov     rcx, [rbx+890h]; this
0x18000abb0  mov     edx, edi; unsigned int
0x18000abb2  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000abb7  test    eax, eax
0x18000abb9  jnz     loc_18000ADDF
0x18000abbf  mov     rcx, [rbx+890h]; this
0x18000abc6  lea     edx, [rdi+7]; unsigned int
0x18000abc9  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000abce  mov     rcx, [rbx+890h]; this
0x18000abd5  mov     edx, edi; unsigned int
0x18000abd7  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000abdc  test    eax, eax
0x18000abde  jnz     loc_18000ADDF
0x18000abe4  mov     rcx, [rbx+890h]; this
0x18000abeb  lea     edx, [rdi+3]; unsigned int
0x18000abee  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000abf3  cmp     eax, edi
0x18000abf5  jnz     loc_18000ADDF
0x18000abfb  mov     rcx, [rbx+890h]; this
0x18000ac02  mov     edx, edi; unsigned int
0x18000ac04  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac09  test    eax, eax
0x18000ac0b  jnz     loc_18000ADDF
0x18000ac11  mov     rcx, [rbx+890h]; this
0x18000ac18  lea     edx, [rdi+1]; unsigned int
0x18000ac1b  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac20  mov     rcx, [rbx+890h]; this
0x18000ac27  mov     edx, edi; unsigned int
0x18000ac29  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac2e  cmp     eax, edi
0x18000ac30  jnz     loc_18000ADDF
0x18000ac36  mov     rcx, [rbx+890h]; this
0x18000ac3d  lea     edx, [rdi+0Fh]; unsigned int
0x18000ac40  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac45  mov     [rbx+34h], eax
0x18000ac48  mov     ecx, edi
0x18000ac4a  mov     [rbx+0B8h], edi
0x18000ac50  cmp     eax, edi
0x18000ac52  jz      short loc_18000AC63
0x18000ac54  sar     eax, 1
0x18000ac56  inc     ecx
0x18000ac58  mov     [rbx+0B8h], ecx
0x18000ac5e  cmp     ecx, 0Fh
0x18000ac61  jle     short loc_18000AC50
0x18000ac63  mov     rcx, [rbx+890h]; this
0x18000ac6a  mov     edx, edi; unsigned int
0x18000ac6c  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac71  cmp     eax, edi
0x18000ac73  jnz     loc_18000ADDF
0x18000ac79  mov     rcx, [rbx+890h]; this
0x18000ac80  mov     edx, edi; unsigned int
0x18000ac82  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac87  test    eax, eax
0x18000ac89  jnz     loc_18000ADDF
0x18000ac8f  mov     rcx, [rbx+890h]; this
0x18000ac96  mov     edx, edi; unsigned int
0x18000ac98  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ac9d  cmp     eax, edi
0x18000ac9f  jnz     loc_18000ADDF
0x18000aca5  mov     rcx, [rbx+890h]; this
0x18000acac  mov     edx, 0Dh; unsigned int
0x18000acb1  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000acb6  cmp     eax, edi
0x18000acb8  jl      loc_18000ADDF
0x18000acbe  mov     rcx, [rbx+890h]; this
0x18000acc5  mov     edx, edi; unsigned int
0x18000acc7  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000accc  cmp     eax, edi
0x18000acce  jnz     loc_18000ADDF
0x18000acd4  mov     rcx, [rbx+890h]; this
0x18000acdb  mov     edx, 0Dh; unsigned int
0x18000ace0  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ace5  cmp     eax, edi
0x18000ace7  jl      loc_18000ADDF
0x18000aced  mov     rcx, [rbx+890h]; this
0x18000acf4  mov     edx, edi; unsigned int
0x18000acf6  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000acfb  cmp     eax, edi
0x18000acfd  jnz     loc_18000ADDF
0x18000ad03  mov     rcx, [rbx+890h]; this
0x18000ad0a  mov     edx, edi; unsigned int
0x18000ad0c  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ad11  test    eax, eax
0x18000ad13  jnz     loc_18000ADDF
0x18000ad19  mov     rcx, [rbx+890h]; this
0x18000ad20  mov     edx, edi; unsigned int
0x18000ad22  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ad27  cmp     eax, edi
0x18000ad29  jnz     loc_18000ADDF
0x18000ad2f  mov     rcx, [rbx+890h]; this
0x18000ad36  mov     edx, edi; unsigned int
0x18000ad38  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ad3d  test    eax, eax
0x18000ad3f  jnz     loc_18000ADDF
0x18000ad45  mov     rcx, [rbx+890h]; this
0x18000ad4c  mov     edx, edi; unsigned int
0x18000ad4e  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ad53  test    eax, eax
0x18000ad55  jnz     loc_18000ADDF
0x18000ad5b  mov     rcx, [rbx+890h]; this
0x18000ad62  mov     edx, edi; unsigned int
0x18000ad64  mov     dword ptr [rbx+38h], 5
0x18000ad6b  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ad70  mov     rcx, [rbx+890h]; this
0x18000ad77  mov     edx, edi; unsigned int
0x18000ad79  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ad7e  test    eax, eax
0x18000ad80  jz      short loc_18000ADDF
0x18000ad82  mov     rcx, [rbx+890h]; this
0x18000ad89  mov     edx, edi; unsigned int
0x18000ad8b  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ad90  mov     rcx, [rbx+890h]; this
0x18000ad97  mov     edx, edi; unsigned int
0x18000ad99  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ad9e  cmp     eax, edi
0x18000ada0  jz      short loc_18000ADDF
0x18000ada2  mov     rcx, [rbx+890h]; this
0x18000ada9  mov     edx, edi; unsigned int
0x18000adab  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000adb0  test    eax, eax
0x18000adb2  jnz     short loc_18000ADDF
0x18000adb4  mov     rcx, [rbx+890h]; this
0x18000adbb  mov     eax, [rcx+10h]
0x18000adbe  mov     edx, eax
0x18000adc0  and     edx, 7; unsigned int
0x18000adc3  jnz     short loc_18000ADCC
0x18000adc5  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000adca  jmp     short loc_18000ADD1
0x18000adcc  sub     eax, edx
0x18000adce  mov     [rcx+10h], eax
0x18000add1  xor     edx, edx; int
0x18000add3  mov     rcx, rbx; this
0x18000add6  call    ?setSliceCode@CVideoObjectDecoder@@AEAAJJ@Z; CVideoObjectDecoder::setSliceCode(long)
0x18000addb  xor     eax, eax
0x18000addd  jmp     short loc_18000ADE4
0x18000addf  mov     eax, 0FFFFFF9Ch
0x18000ade4  mov     rbx, [rsp+28h+arg_0]
0x18000ade9  add     rsp, 20h
0x18000aded  pop     rdi
0x18000adee  retn
```
