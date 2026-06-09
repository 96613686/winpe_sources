# CVideoObjectDecoder::setSliceCode(long)

- ea: `0x18000b198`
- end: `0x18000b2cb`
- name: `?setSliceCode@CVideoObjectDecoder@@AEAAJJ@Z`
- size: `307`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aa50`
- `0x18000ad38`

## callees

- `0x18000b198`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::setSliceCode(CVideoObjectDecoder *this, int a2)
{
  unsigned int v2; // eax
  int v4; // ecx
  __int64 (__fastcall *v5)(CVideoObjectDecoder *__hidden, struct CDCTTableInfo_Dec *); // r9
  __int64 (__fastcall *v6)(CVideoObjectDecoder *__hidden, struct CMBMode *); // r10
  __int64 (__fastcall *v7)(CVideoObjectDecoder *__hidden, struct CMBMode *, int, int); // r11
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
      v6 = CVideoObjectDecoder::decodeMBOverheadOfPVOP_New;
      v7 = CVideoObjectDecoder::decodeMBOverheadOfIVOP_New;
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
      v6 = CVideoObjectDecoder::decodeMBOverheadOfPVOP_MSV;
      v7 = CVideoObjectDecoder::decodeMBOverheadOfIVOP_MSV;
    }
    v5 = CVideoObjectDecoder::DecodeInverseInterBlockQuantizeEscCode;
    v2 = *((_DWORD *)this + 29) / (unsigned int)(a2 - 22);
    goto LABEL_13;
  }
  *((_DWORD *)this + 389) = 0;
  if ( a2 <= 0 )
    return 4294967196LL;
  v5 = CVideoObjectDecoder::DecodeInverseInterBlockQuantize;
  v6 = CVideoObjectDecoder::decodeMBOverheadOfPVOP_Old;
  v7 = CVideoObjectDecoder::decodeMBOverheadOfIVOP_Old;
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
0x18000b198  cmp     dword ptr [rcx+0E9Ch], 0
0x18000b19f  mov     eax, edx
0x18000b1a1  mov     r8, rcx
0x18000b1a4  jnz     loc_18000B2C8
0x18000b1aa  mov     ecx, [rcx+8]
0x18000b1ad  cmp     ecx, 1
0x18000b1b0  jnz     short loc_18000B1DF
0x18000b1b2  mov     dword ptr [r8+614h], 0
0x18000b1bd  test    eax, eax
0x18000b1bf  jle     loc_18000B289
0x18000b1c5  lea     r9, ?DecodeInverseInterBlockQuantize@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@@Z; CVideoObjectDecoder::DecodeInverseInterBlockQuantize(CDCTTableInfo_Dec *)
0x18000b1cc  lea     r10, ?decodeMBOverheadOfPVOP_Old@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@@Z; CVideoObjectDecoder::decodeMBOverheadOfPVOP_Old(CMBMode *)
0x18000b1d3  lea     r11, ?decodeMBOverheadOfIVOP_Old@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@JJ@Z; CVideoObjectDecoder::decodeMBOverheadOfIVOP_Old(CMBMode *,long,long)
0x18000b1da  jmp     loc_18000B263
0x18000b1df  mov     dword ptr [r8+614h], 1
0x18000b1ea  cmp     ecx, 2
0x18000b1ed  jnz     short loc_18000B225
0x18000b1ef  mov     dword ptr [r8+95Ch], 0
0x18000b1fa  cmp     eax, 16h
0x18000b1fd  jle     loc_18000B289
0x18000b203  lea     r10, ?decodeMBOverheadOfPVOP_New@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@@Z; CVideoObjectDecoder::decodeMBOverheadOfPVOP_New(CMBMode *)
0x18000b20a  lea     r11, ?decodeMBOverheadOfIVOP_New@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@JJ@Z; CVideoObjectDecoder::decodeMBOverheadOfIVOP_New(CMBMode *,long,long)
0x18000b211  mov     eax, [r8+74h]
0x18000b215  lea     ecx, [rdx-16h]
0x18000b218  xor     edx, edx
0x18000b21a  lea     r9, ?DecodeInverseInterBlockQuantizeEscCode@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@@Z; CVideoObjectDecoder::DecodeInverseInterBlockQuantizeEscCode(CDCTTableInfo_Dec *)
0x18000b221  div     ecx
0x18000b223  jmp     short loc_18000B263
0x18000b225  cmp     ecx, 3
0x18000b228  jl      short loc_18000B24A
0x18000b22a  mov     dword ptr [r8+95Ch], 1
0x18000b235  cmp     eax, 16h
0x18000b238  jle     short loc_18000B289
0x18000b23a  lea     r10, ?decodeMBOverheadOfPVOP_MSV@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@@Z; CVideoObjectDecoder::decodeMBOverheadOfPVOP_MSV(CMBMode *)
0x18000b241  lea     r11, ?decodeMBOverheadOfIVOP_MSV@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@JJ@Z; CVideoObjectDecoder::decodeMBOverheadOfIVOP_MSV(CMBMode *,long,long)
0x18000b248  jmp     short loc_18000B211
0x18000b24a  mov     eax, [r8+74h]
0x18000b24e  lea     r9, ?DecodeInverseInterBlockQuantizeEscCode_MPEG4@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@@Z; CVideoObjectDecoder::DecodeInverseInterBlockQuantizeEscCode_MPEG4(CDCTTableInfo_Dec *)
0x18000b255  lea     r10, ?decodeMBOverheadOfPVOP_MPEG4@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@@Z; CVideoObjectDecoder::decodeMBOverheadOfPVOP_MPEG4(CMBMode *)
0x18000b25c  lea     r11, ?decodeMBOverheadOfIVOP_MPEG4@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@JJ@Z; CVideoObjectDecoder::decodeMBOverheadOfIVOP_MPEG4(CMBMode *,long,long)
0x18000b263  mov     ecx, 80h
0x18000b268  mov     rdx, r8
0x18000b26b  mov     [rdx+rcx], eax
0x18000b26e  mov     [r8+0E28h], r11
0x18000b275  mov     [r8+0E30h], r10
0x18000b27c  mov     [r8+0E48h], r9
0x18000b283  cmp     dword ptr [rdx+rcx], 0
0x18000b287  jnz     short loc_18000B28F
0x18000b289  mov     eax, 0FFFFFF9Ch
0x18000b28e  retn
0x18000b28f  cmp     dword ptr [r8+0ECCh], 0
0x18000b297  jnz     short loc_18000B2B4
0x18000b299  cmp     dword ptr [r8+120h], 0
0x18000b2a1  jz      short loc_18000B2B4
0x18000b2a3  cmp     dword ptr [r8+614h], 0
0x18000b2ab  jz      short loc_18000B2B4
0x18000b2ad  mov     eax, 1
0x18000b2b2  jmp     short loc_18000B2B6
0x18000b2b4  xor     eax, eax
0x18000b2b6  mov     [r8+610h], eax
0x18000b2bd  mov     dword ptr [r8+0E9Ch], 1
0x18000b2c8  xor     eax, eax
0x18000b2ca  retn
```
