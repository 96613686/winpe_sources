# CVideoObjectDecoder::setSliceCode(long)

- ea: `0x180028edc`
- end: `0x180028f6e`
- name: `?setSliceCode@CVideoObjectDecoder@@AEAAJJ@Z`
- size: `146`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ab70`
- `0x18001f53c`
- `0x180028ea4`

## callees

- `0x180028edc`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::setSliceCode(CVideoObjectDecoder *this)
{
  int v1; // edx
  __int64 (__fastcall *v2)(CVideoObjectDecoder *__hidden, struct CMBMode *, int, int); // rax
  __int64 (__fastcall *v3)(CVideoObjectDecoder *__hidden, struct CMBMode *); // rax
  bool v4; // zf
  __int64 (__fastcall *v5)(CVideoObjectDecoder *__hidden, struct CDCTTableInfo_Dec *); // rax

  if ( !*((_DWORD *)this + 1901) )
  {
    v1 = *((_DWORD *)this + 2);
    *((_DWORD *)this + 226) = *((_DWORD *)this + 223);
    *((_DWORD *)this + 650) = 1;
    v2 = CVideoObjectDecoder::decodeMBOverheadOfIVOP_MPEG4;
    if ( v1 )
      v2 = CVideoObjectDecoder::decodeMBOverheadOfIVOP_M4S2;
    *((_QWORD *)this + 827) = v2;
    v3 = CVideoObjectDecoder::decodeMBOverheadOfPVOP_MPEG4;
    if ( v1 )
      v3 = CVideoObjectDecoder::decodeMBOverheadOfPVOP_M4S2;
    *((_QWORD *)this + 828) = v3;
    v4 = *((_DWORD *)this + 17) == 0;
    *((_QWORD *)this + 829) = CVideoObjectDecoder::decodeMBOverheadOfBVOP_M4S2;
    v5 = CVideoObjectDecoder::DecodeInverseInterBlockQuantizeEscCodeRVLC_MPEG4;
    if ( v4 )
      v5 = CVideoObjectDecoder::DecodeInverseInterBlockQuantizeEscCode_MPEG4;
    *((_QWORD *)this + 938) = v5;
    *((_DWORD *)this + 1901) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180028edc  cmp     dword ptr [rcx+1DB4h], 0
0x180028ee3  jnz     loc_180028F6B
0x180028ee9  mov     eax, [rcx+37Ch]
0x180028eef  lea     r8, ?decodeMBOverheadOfIVOP_M4S2@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@JJ@Z; CVideoObjectDecoder::decodeMBOverheadOfIVOP_M4S2(CMBMode *,long,long)
0x180028ef6  mov     edx, [rcx+8]
0x180028ef9  mov     r9d, 1
0x180028eff  mov     [rcx+388h], eax
0x180028f05  test    edx, edx
0x180028f07  mov     [rcx+0A28h], r9d
0x180028f0e  lea     rax, ?decodeMBOverheadOfIVOP_MPEG4@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@JJ@Z; CVideoObjectDecoder::decodeMBOverheadOfIVOP_MPEG4(CMBMode *,long,long)
0x180028f15  cmovnz  rax, r8
0x180028f19  lea     rdx, ?DecodeInverseInterBlockQuantizeEscCode_MPEG4@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@@Z; CVideoObjectDecoder::DecodeInverseInterBlockQuantizeEscCode_MPEG4(CDCTTableInfo_Dec *)
0x180028f20  mov     [rcx+19D8h], rax
0x180028f27  lea     r8, ?decodeMBOverheadOfPVOP_M4S2@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@@Z; CVideoObjectDecoder::decodeMBOverheadOfPVOP_M4S2(CMBMode *)
0x180028f2e  lea     rax, ?decodeMBOverheadOfPVOP_MPEG4@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@@Z; CVideoObjectDecoder::decodeMBOverheadOfPVOP_MPEG4(CMBMode *)
0x180028f35  cmovnz  rax, r8
0x180028f39  mov     [rcx+19E0h], rax
0x180028f40  lea     rax, ?decodeMBOverheadOfBVOP_M4S2@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@@Z; CVideoObjectDecoder::decodeMBOverheadOfBVOP_M4S2(CMBMode *)
0x180028f47  cmp     dword ptr [rcx+44h], 0
0x180028f4b  mov     [rcx+19E8h], rax
0x180028f52  lea     rax, ?DecodeInverseInterBlockQuantizeEscCodeRVLC_MPEG4@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@@Z; CVideoObjectDecoder::DecodeInverseInterBlockQuantizeEscCodeRVLC_MPEG4(CDCTTableInfo_Dec *)
0x180028f59  cmovz   rax, rdx
0x180028f5d  mov     [rcx+1D50h], rax
0x180028f64  mov     [rcx+1DB4h], r9d
0x180028f6b  xor     eax, eax
0x180028f6d  retn
```
