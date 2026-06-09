# CVideoObjectDecoder::setSliceCode(long)

- ea: `0x18000b258`
- end: `0x18000b38b`
- name: `?setSliceCode@CVideoObjectDecoder@@AEAAJJ@Z`
- size: `307`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ab10`
- `0x18000adf8`

## callees

- `0x18000b258`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::setSliceCode(CVideoObjectDecoder *this, int a2)
{
  unsigned int v2; // eax
  int v4; // ecx
  __int64 (__fastcall *v5)(CVideoObjectDecoder *, Huffman **); // r9
  __int64 (__fastcall *v6)(CInputBitStream **, struct CMBMode *); // r10
  __int64 (__fastcall *v7)(CInputBitStream **, struct CMBMode *); // r11
  BOOL v9; // eax

  v2 = a2;
  if ( *((_DWORD *)this + 935) )
    return 0;
  v4 = *((_DWORD *)this + 2);
  if ( v4 != 1 )
  {
    *((_DWORD *)this + 389) = 1;
    if ( v4 == 2 )
    {
      *((_DWORD *)this + 599) = 0;
      if ( a2 <= 22 )
        return 4294967196LL;
      v6 = (__int64 (__fastcall *)(CInputBitStream **, struct CMBMode *))CVideoObjectDecoder::decodeMBOverheadOfPVOP_New;
      v7 = (__int64 (__fastcall *)(CInputBitStream **, struct CMBMode *))CVideoObjectDecoder::decodeMBOverheadOfIVOP_New;
    }
    else
    {
      if ( v4 < 3 )
      {
        v2 = *((_DWORD *)this + 29);
        v5 = CVideoObjectDecoder::DecodeInverseInterBlockQuantizeEscCode_MPEG4;
        v6 = CVideoObjectDecoder::decodeMBOverheadOfPVOP_MPEG4;
        v7 = CVideoObjectDecoder::decodeMBOverheadOfIVOP_MPEG4;
        goto LABEL_13;
      }
      *((_DWORD *)this + 599) = 1;
      if ( a2 <= 22 )
        return 4294967196LL;
      v6 = (__int64 (__fastcall *)(CInputBitStream **, struct CMBMode *))CVideoObjectDecoder::decodeMBOverheadOfPVOP_MSV;
      v7 = (__int64 (__fastcall *)(CInputBitStream **, struct CMBMode *))CVideoObjectDecoder::decodeMBOverheadOfIVOP_MSV;
    }
    v5 = CVideoObjectDecoder::DecodeInverseInterBlockQuantizeEscCode;
    v2 = *((_DWORD *)this + 29) / (unsigned int)(a2 - 22);
    goto LABEL_13;
  }
  *((_DWORD *)this + 389) = 0;
  if ( a2 <= 0 )
    return 4294967196LL;
  v5 = (__int64 (__fastcall *)(CVideoObjectDecoder *, Huffman **))CVideoObjectDecoder::DecodeInverseInterBlockQuantize;
  v6 = (__int64 (__fastcall *)(CInputBitStream **, struct CMBMode *))CVideoObjectDecoder::decodeMBOverheadOfPVOP_Old;
  v7 = (__int64 (__fastcall *)(CInputBitStream **, struct CMBMode *))CVideoObjectDecoder::decodeMBOverheadOfIVOP_Old;
LABEL_13:
  *((_DWORD *)this + 32) = v2;
  *((_QWORD *)this + 453) = v7;
  *((_QWORD *)this + 454) = v6;
  *((_QWORD *)this + 457) = v5;
  if ( !*((_DWORD *)this + 32) )
    return 4294967196LL;
  v9 = !*((_DWORD *)this + 947) && *((_DWORD *)this + 72) && *((_DWORD *)this + 389);
  *((_DWORD *)this + 388) = v9;
  *((_DWORD *)this + 935) = 1;
  return 0;
}

```

## disassembly

```asm
0x18000b258  cmp     dword ptr [rcx+0E9Ch], 0
0x18000b25f  mov     eax, edx
0x18000b261  mov     r8, rcx
0x18000b264  jnz     loc_18000B388
0x18000b26a  mov     ecx, [rcx+8]
0x18000b26d  cmp     ecx, 1
0x18000b270  jnz     short loc_18000B29F
0x18000b272  mov     dword ptr [r8+614h], 0
0x18000b27d  test    eax, eax
0x18000b27f  jle     loc_18000B349
0x18000b285  lea     r9, ?DecodeInverseInterBlockQuantize@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@@Z; CVideoObjectDecoder::DecodeInverseInterBlockQuantize(CDCTTableInfo_Dec *)
0x18000b28c  lea     r10, ?decodeMBOverheadOfPVOP_Old@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@@Z; CVideoObjectDecoder::decodeMBOverheadOfPVOP_Old(CMBMode *)
0x18000b293  lea     r11, ?decodeMBOverheadOfIVOP_Old@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@JJ@Z; CVideoObjectDecoder::decodeMBOverheadOfIVOP_Old(CMBMode *,long,long)
0x18000b29a  jmp     loc_18000B323
0x18000b29f  mov     dword ptr [r8+614h], 1
0x18000b2aa  cmp     ecx, 2
0x18000b2ad  jnz     short loc_18000B2E5
0x18000b2af  mov     dword ptr [r8+95Ch], 0
0x18000b2ba  cmp     eax, 16h
0x18000b2bd  jle     loc_18000B349
0x18000b2c3  lea     r10, ?decodeMBOverheadOfPVOP_New@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@@Z; CVideoObjectDecoder::decodeMBOverheadOfPVOP_New(CMBMode *)
0x18000b2ca  lea     r11, ?decodeMBOverheadOfIVOP_New@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@JJ@Z; CVideoObjectDecoder::decodeMBOverheadOfIVOP_New(CMBMode *,long,long)
0x18000b2d1  mov     eax, [r8+74h]
0x18000b2d5  lea     ecx, [rdx-16h]
0x18000b2d8  xor     edx, edx
0x18000b2da  lea     r9, ?DecodeInverseInterBlockQuantizeEscCode@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@@Z; CVideoObjectDecoder::DecodeInverseInterBlockQuantizeEscCode(CDCTTableInfo_Dec *)
0x18000b2e1  div     ecx
0x18000b2e3  jmp     short loc_18000B323
0x18000b2e5  cmp     ecx, 3
0x18000b2e8  jl      short loc_18000B30A
0x18000b2ea  mov     dword ptr [r8+95Ch], 1
0x18000b2f5  cmp     eax, 16h
0x18000b2f8  jle     short loc_18000B349
0x18000b2fa  lea     r10, ?decodeMBOverheadOfPVOP_MSV@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@@Z; CVideoObjectDecoder::decodeMBOverheadOfPVOP_MSV(CMBMode *)
0x18000b301  lea     r11, ?decodeMBOverheadOfIVOP_MSV@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@JJ@Z; CVideoObjectDecoder::decodeMBOverheadOfIVOP_MSV(CMBMode *,long,long)
0x18000b308  jmp     short loc_18000B2D1
0x18000b30a  mov     eax, [r8+74h]
0x18000b30e  lea     r9, ?DecodeInverseInterBlockQuantizeEscCode_MPEG4@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@@Z; CVideoObjectDecoder::DecodeInverseInterBlockQuantizeEscCode_MPEG4(CDCTTableInfo_Dec *)
0x18000b315  lea     r10, ?decodeMBOverheadOfPVOP_MPEG4@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@@Z; CVideoObjectDecoder::decodeMBOverheadOfPVOP_MPEG4(CMBMode *)
0x18000b31c  lea     r11, ?decodeMBOverheadOfIVOP_MPEG4@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@JJ@Z; CVideoObjectDecoder::decodeMBOverheadOfIVOP_MPEG4(CMBMode *,long,long)
0x18000b323  mov     ecx, 80h
0x18000b328  mov     rdx, r8
0x18000b32b  mov     [rdx+rcx], eax
0x18000b32e  mov     [r8+0E28h], r11
0x18000b335  mov     [r8+0E30h], r10
0x18000b33c  mov     [r8+0E48h], r9
0x18000b343  cmp     dword ptr [rdx+rcx], 0
0x18000b347  jnz     short loc_18000B34F
0x18000b349  mov     eax, 0FFFFFF9Ch
0x18000b34e  retn
0x18000b34f  cmp     dword ptr [r8+0ECCh], 0
0x18000b357  jnz     short loc_18000B374
0x18000b359  cmp     dword ptr [r8+120h], 0
0x18000b361  jz      short loc_18000B374
0x18000b363  cmp     dword ptr [r8+614h], 0
0x18000b36b  jz      short loc_18000B374
0x18000b36d  mov     eax, 1
0x18000b372  jmp     short loc_18000B376
0x18000b374  xor     eax, eax
0x18000b376  mov     [r8+610h], eax
0x18000b37d  mov     dword ptr [r8+0E9Ch], 1
0x18000b388  xor     eax, eax
0x18000b38a  retn
```
