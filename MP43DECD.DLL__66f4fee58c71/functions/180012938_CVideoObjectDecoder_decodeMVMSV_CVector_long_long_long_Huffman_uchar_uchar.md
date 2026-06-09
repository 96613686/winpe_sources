# CVideoObjectDecoder::decodeMVMSV(CVector *,long,long,long,Huffman *,uchar *,uchar *)

- ea: `0x180012938`
- end: `0x180012a45`
- name: `?decodeMVMSV@CVideoObjectDecoder@@AEAAJPEAVCVector@@JJJPEAVHuffman@@PEAE2@Z`
- size: `269`
- prototype: `int(CVideoObjectDecoder *__hidden this, struct CVector *, int, int, int, struct Huffman *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180010600`
- `0x180010f80`
- `0x1800119e8`

## callees

- `0x18000b0ac`
- `0x180012938`
- `0x180012a4c`
- `0x18001ed9c`

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
0x180012938  mov     r11, rsp
0x18001293b  mov     [r11+10h], rbx
0x18001293f  mov     [r11+18h], rsi
0x180012943  push    rdi
0x180012944  sub     rsp, 30h
0x180012948  mov     eax, [rsp+38h+arg_20]
0x18001294c  mov     rsi, rdx
0x18001294f  mov     [rsp+38h+var_10], eax; int
0x180012953  mov     rbx, rcx
0x180012956  mov     [r11-18h], r9d
0x18001295a  mov     r9d, r8d; int
0x18001295d  mov     r8, rdx; struct CVector *
0x180012960  mov     [rsp+38h+arg_0], 0
0x180012967  lea     rdx, [r11+8]; struct CVector *
0x18001296b  call    ?find16x16MVpred@CVideoObjectDecoder@@AEBAXAEAVCVector@@PEBV2@JJJ@Z; CVideoObjectDecoder::find16x16MVpred(CVector &,CVector const *,long,long,long)
0x180012970  mov     rdx, [rbx+890h]; struct CInputBitStream *
0x180012977  mov     rcx, [rsp+38h+arg_28]; this
0x18001297c  call    ?get@Huffman@@QEAAJPEAVCInputBitStream@@@Z; Huffman::get(CInputBitStream *)
0x180012981  mov     rcx, [rbx+890h]; this
0x180012988  cmp     dword ptr [rcx+14h], 0
0x18001298c  jnz     loc_180012A30
0x180012992  cmp     eax, 44Bh
0x180012997  jz      short loc_1800129B1
0x180012999  movsxd  rcx, eax
0x18001299c  mov     rax, [rsp+38h+arg_30]
0x1800129a1  movzx   edi, byte ptr [rcx+rax]
0x1800129a5  mov     rax, [rsp+38h+arg_38]
0x1800129aa  movzx   r9d, byte ptr [rcx+rax]
0x1800129af  jmp     short loc_1800129DE
0x1800129b1  mov     edx, 6; unsigned int
0x1800129b6  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x1800129bb  mov     rcx, [rbx+890h]; this
0x1800129c2  mov     edx, 6; unsigned int
0x1800129c7  mov     edi, eax
0x1800129c9  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x1800129ce  mov     rcx, [rbx+890h]
0x1800129d5  mov     r9d, eax
0x1800129d8  cmp     dword ptr [rcx+14h], 0
0x1800129dc  jnz     short loc_180012A30
0x1800129de  movsx   edx, byte ptr [rsp+38h+arg_0]
0x1800129e3  lea     r8, [rbx+0E60h]
0x1800129ea  add     edx, 0FFFFFFE0h
0x1800129ed  mov     r10b, 40h ; '@'
0x1800129f0  add     edx, edi
0x1800129f2  cmp     edx, [rbx+0E64h]
0x1800129f8  jle     short loc_1800129FF
0x1800129fa  sub     dl, r10b
0x1800129fd  jmp     short loc_180012A07
0x1800129ff  cmp     edx, [r8]
0x180012a02  jge     short loc_180012A07
0x180012a04  add     dl, r10b
0x180012a07  mov     [rsi], dl
0x180012a09  movsx   ecx, byte ptr [rsp+38h+arg_0+1]
0x180012a0e  add     ecx, 0FFFFFFE0h
0x180012a11  add     ecx, r9d
0x180012a14  cmp     ecx, [rbx+0E64h]
0x180012a1a  jle     short loc_180012A21
0x180012a1c  sub     cl, r10b
0x180012a1f  jmp     short loc_180012A29
0x180012a21  cmp     ecx, [r8]
0x180012a24  jge     short loc_180012A29
0x180012a26  add     cl, r10b
0x180012a29  mov     [rsi+1], cl
0x180012a2c  xor     eax, eax
0x180012a2e  jmp     short loc_180012A35
0x180012a30  mov     eax, 0FFFFFF9Ch
0x180012a35  mov     rbx, [rsp+38h+arg_8]
0x180012a3a  mov     rsi, [rsp+38h+arg_10]
0x180012a3f  add     rsp, 30h
0x180012a43  pop     rdi
0x180012a44  retn
```
