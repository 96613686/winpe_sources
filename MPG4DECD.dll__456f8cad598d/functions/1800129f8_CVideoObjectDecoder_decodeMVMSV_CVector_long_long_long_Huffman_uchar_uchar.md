# CVideoObjectDecoder::decodeMVMSV(CVector *,long,long,long,Huffman *,uchar *,uchar *)

- ea: `0x1800129f8`
- end: `0x180012b05`
- name: `?decodeMVMSV@CVideoObjectDecoder@@AEAAJPEAVCVector@@JJJPEAVHuffman@@PEAE2@Z`
- size: `269`
- prototype: `__int64 __fastcall(struct CInputBitStream **this, struct CVector *, int, int, int, struct Huffman *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800106c0`
- `0x180011040`
- `0x180011aa8`

## callees

- `0x18000b16c`
- `0x1800129f8`
- `0x180012b0c`
- `0x18001ee5c`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::decodeMVMSV(
        struct CInputBitStream **this,
        struct CVector *a2,
        int a3,
        int a4,
        int a5,
        struct Huffman *a6,
        unsigned __int8 *a7,
        unsigned __int8 *a8)
{
  int v10; // eax
  CInputBitStream *v11; // rcx
  unsigned int Bits; // edi
  unsigned int v13; // r9d
  signed int *v14; // r8
  signed int v15; // edx
  signed int v16; // ecx
  __int16 v18; // [rsp+40h] [rbp+8h] BYREF

  v18 = 0;
  CVideoObjectDecoder::find16x16MVpred((CVideoObjectDecoder *)this, (struct CVector *)&v18, a2, a3, a4, a5);
  v10 = Huffman::get(a6, this[274]);
  v11 = this[274];
  if ( *((_DWORD *)v11 + 5) )
    return 4294967196LL;
  if ( v10 == 1099 )
  {
    Bits = CInputBitStream::getBits(v11, 6u);
    v13 = CInputBitStream::getBits(this[274], 6u);
    if ( !*((_DWORD *)this[274] + 5) )
      goto LABEL_5;
    return 4294967196LL;
  }
  Bits = a7[v10];
  v13 = a8[v10];
LABEL_5:
  v14 = (signed int *)(this + 460);
  v15 = Bits + (char)v18 - 32;
  if ( v15 <= *((_DWORD *)this + 921) )
  {
    if ( v15 < *v14 )
      LOBYTE(v15) = v15 + 64;
  }
  else
  {
    LOBYTE(v15) = v15 - 64;
  }
  *(_BYTE *)a2 = v15;
  v16 = v13 + SHIBYTE(v18) - 32;
  if ( v16 <= *((_DWORD *)this + 921) )
  {
    if ( v16 < *v14 )
      LOBYTE(v16) = v16 + 64;
  }
  else
  {
    LOBYTE(v16) = v16 - 64;
  }
  *((_BYTE *)a2 + 1) = v16;
  return 0;
}

```

## disassembly

```asm
0x1800129f8  mov     r11, rsp
0x1800129fb  mov     [r11+10h], rbx
0x1800129ff  mov     [r11+18h], rsi
0x180012a03  push    rdi
0x180012a04  sub     rsp, 30h
0x180012a08  mov     eax, [rsp+38h+arg_20]
0x180012a0c  mov     rsi, rdx
0x180012a0f  mov     [rsp+38h+var_10], eax; int
0x180012a13  mov     rbx, rcx
0x180012a16  mov     [r11-18h], r9d
0x180012a1a  mov     r9d, r8d; int
0x180012a1d  mov     r8, rdx; struct CVector *
0x180012a20  mov     [rsp+38h+arg_0], 0
0x180012a27  lea     rdx, [r11+8]; struct CVector *
0x180012a2b  call    ?find16x16MVpred@CVideoObjectDecoder@@AEBAXAEAVCVector@@PEBV2@JJJ@Z; CVideoObjectDecoder::find16x16MVpred(CVector &,CVector const *,long,long,long)
0x180012a30  mov     rdx, [rbx+890h]; struct CInputBitStream *
0x180012a37  mov     rcx, [rsp+38h+arg_28]; this
0x180012a3c  call    ?get@Huffman@@QEAAJPEAVCInputBitStream@@@Z; Huffman::get(CInputBitStream *)
0x180012a41  mov     rcx, [rbx+890h]; this
0x180012a48  cmp     dword ptr [rcx+14h], 0
0x180012a4c  jnz     loc_180012AF0
0x180012a52  cmp     eax, 44Bh
0x180012a57  jz      short loc_180012A71
0x180012a59  movsxd  rcx, eax
0x180012a5c  mov     rax, [rsp+38h+arg_30]
0x180012a61  movzx   edi, byte ptr [rcx+rax]
0x180012a65  mov     rax, [rsp+38h+arg_38]
0x180012a6a  movzx   r9d, byte ptr [rcx+rax]
0x180012a6f  jmp     short loc_180012A9E
0x180012a71  mov     edx, 6; unsigned int
0x180012a76  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x180012a7b  mov     rcx, [rbx+890h]; this
0x180012a82  mov     edx, 6; unsigned int
0x180012a87  mov     edi, eax
0x180012a89  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x180012a8e  mov     rcx, [rbx+890h]
0x180012a95  mov     r9d, eax
0x180012a98  cmp     dword ptr [rcx+14h], 0
0x180012a9c  jnz     short loc_180012AF0
0x180012a9e  movsx   edx, byte ptr [rsp+38h+arg_0]
0x180012aa3  lea     r8, [rbx+0E60h]
0x180012aaa  add     edx, 0FFFFFFE0h
0x180012aad  mov     r10b, 40h ; '@'
0x180012ab0  add     edx, edi
0x180012ab2  cmp     edx, [rbx+0E64h]
0x180012ab8  jle     short loc_180012ABF
0x180012aba  sub     dl, r10b
0x180012abd  jmp     short loc_180012AC7
0x180012abf  cmp     edx, [r8]
0x180012ac2  jge     short loc_180012AC7
0x180012ac4  add     dl, r10b
0x180012ac7  mov     [rsi], dl
0x180012ac9  movsx   ecx, byte ptr [rsp+38h+arg_0+1]
0x180012ace  add     ecx, 0FFFFFFE0h
0x180012ad1  add     ecx, r9d
0x180012ad4  cmp     ecx, [rbx+0E64h]
0x180012ada  jle     short loc_180012AE1
0x180012adc  sub     cl, r10b
0x180012adf  jmp     short loc_180012AE9
0x180012ae1  cmp     ecx, [r8]
0x180012ae4  jge     short loc_180012AE9
0x180012ae6  add     cl, r10b
0x180012ae9  mov     [rsi+1], cl
0x180012aec  xor     eax, eax
0x180012aee  jmp     short loc_180012AF5
0x180012af0  mov     eax, 0FFFFFF9Ch
0x180012af5  mov     rbx, [rsp+38h+arg_8]
0x180012afa  mov     rsi, [rsp+38h+arg_10]
0x180012aff  add     rsp, 30h
0x180012b03  pop     rdi
0x180012b04  retn
```
