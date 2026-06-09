# CVideoObjectDecoder::DecodeIMB(long const *,uchar *,uchar *,uchar *)

- ea: `0x18000e910`
- end: `0x18000eb71`
- name: `?DecodeIMB@CVideoObjectDecoder@@AEAAJPEBJPEAE11@Z`
- size: `609`
- prototype: `__int64 __usercall@<rax>(CVideoObjectDecoder *__hidden this@<rcx>, const int *@<rdx>, unsigned __int8 *@<r8>, unsigned __int8 *@<r9>, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f440`
- `0x18000f9d0`
- `0x180010600`
- `0x180010f80`

## callees

- `0x18000b0ac`
- `0x18000d684`
- `0x18000dc8c`
- `0x18000e910`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::DecodeIMB(
        CVideoObjectDecoder *this,
        const int *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5)
{
  struct CDCTTableInfo_Dec *v5; // r13
  __int64 v6; // rdi
  struct CDCTTableInfo_Dec *v7; // r12
  unsigned __int8 MaxBits; // al
  CInputBitStream *v12; // rcx
  unsigned __int8 v13; // bp
  unsigned __int8 Bits; // al
  int v15; // r8d
  int v16; // edx
  int v17; // eax
  __int64 result; // rax
  int v19; // eax
  unsigned __int8 v20; // al
  CInputBitStream *v21; // rcx
  unsigned __int8 v22; // di
  unsigned __int8 v23; // al
  int v24; // r8d
  int v25; // edx
  int v26; // eax
  unsigned __int8 v27; // al
  CInputBitStream *v28; // rcx
  unsigned __int8 v29; // di
  unsigned __int8 v30; // al
  int v31; // r8d
  int v32; // edx
  int v33; // eax

  v5 = (struct CDCTTableInfo_Dec *)*((_QWORD *)this + 439);
  v6 = 0;
  v7 = (struct CDCTTableInfo_Dec *)*((_QWORD *)this + 440);
  while ( 1 )
  {
    MaxBits = CInputBitStream::getMaxBits(*((CInputBitStream **)this + 274), 7u, &gDecodeCodeTableIntraDCy);
    v12 = (CInputBitStream *)*((_QWORD *)this + 274);
    if ( *((_DWORD *)v12 + 5) )
      return 4294967196LL;
    if ( MaxBits )
    {
      v13 = MaxBits;
      Bits = CInputBitStream::getBits(v12, MaxBits);
      if ( *(_DWORD *)(*((_QWORD *)this + 274) + 20LL) )
        return 4294967196LL;
      v15 = *((_DWORD *)this + 80);
      v16 = Bits;
      if ( _bittest(&v16, (unsigned __int8)(v13 - 1)) )
        v17 = Bits + v15;
      else
        v17 = Bits - (1 << v13) + v15 + 1;
      *((_DWORD *)this + 80) = v17;
    }
    *((_DWORD *)this + 404) = *((_DWORD *)this + 80) * *((_DWORD *)this + 91);
    result = CVideoObjectDecoder::decodeIntraBlock(this, v7, a2[v6], a3, *((_DWORD *)this + 84));
    if ( (_DWORD)result )
      return result;
    v19 = 8;
    if ( (_DWORD)v6 == 1 )
      v19 = *((_DWORD *)this + 924);
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 4 )
      break;
    a3 += v19;
  }
  v20 = CInputBitStream::getMaxBits(*((CInputBitStream **)this + 274), 8u, &gDecodeCodeTableIntraDCc);
  v21 = (CInputBitStream *)*((_QWORD *)this + 274);
  if ( !*((_DWORD *)v21 + 5) )
  {
    if ( v20 )
    {
      v22 = v20;
      v23 = CInputBitStream::getBits(v21, v20);
      if ( *(_DWORD *)(*((_QWORD *)this + 274) + 20LL) )
        return 4294967196LL;
      v24 = *((_DWORD *)this + 81);
      v25 = v23;
      if ( _bittest(&v25, (unsigned __int8)(v22 - 1)) )
        v26 = v23 + v24;
      else
        v26 = v23 - (1 << v22) + v24 + 1;
      *((_DWORD *)this + 81) = v26;
    }
    *((_DWORD *)this + 404) = 8 * *((_DWORD *)this + 81);
    result = CVideoObjectDecoder::decodeIntraBlock(this, v5, a2[4], a4, *((_DWORD *)this + 85));
    if ( (_DWORD)result )
      return result;
    v27 = CInputBitStream::getMaxBits(*((CInputBitStream **)this + 274), 8u, &gDecodeCodeTableIntraDCc);
    v28 = (CInputBitStream *)*((_QWORD *)this + 274);
    if ( !*((_DWORD *)v28 + 5) )
    {
      if ( !v27 )
      {
LABEL_29:
        *((_DWORD *)this + 404) = 8 * *((_DWORD *)this + 82);
        return CVideoObjectDecoder::decodeIntraBlock(this, v5, a2[5], a5, *((_DWORD *)this + 85));
      }
      v29 = v27;
      v30 = CInputBitStream::getBits(v28, v27);
      if ( !*(_DWORD *)(*((_QWORD *)this + 274) + 20LL) )
      {
        v31 = *((_DWORD *)this + 82);
        v32 = v30;
        if ( _bittest(&v32, (unsigned __int8)(v29 - 1)) )
          v33 = v30 + v31;
        else
          v33 = v30 - (1 << v29) + v31 + 1;
        *((_DWORD *)this + 82) = v33;
        goto LABEL_29;
      }
    }
  }
  return 4294967196LL;
}

```

## disassembly

```asm
0x18000e910  mov     [rsp+arg_18], r9
0x18000e915  push    rbx
0x18000e916  push    rbp
0x18000e917  push    rsi
0x18000e918  push    rdi
0x18000e919  push    r12
0x18000e91b  push    r13
0x18000e91d  push    r14
0x18000e91f  push    r15
0x18000e921  sub     rsp, 38h
0x18000e925  mov     r13, [rcx+0DB8h]
0x18000e92c  xor     edi, edi
0x18000e92e  mov     r12, [rcx+0DC0h]
0x18000e935  mov     r14, r8
0x18000e938  mov     r15, rdx
0x18000e93b  mov     rbx, rcx
0x18000e93e  lea     esi, [rdi+1]
0x18000e941  mov     rcx, [rbx+890h]; this
0x18000e948  lea     r8, ?gDecodeCodeTableIntraDCy@@3PAEA; unsigned __int8 *
0x18000e94f  mov     edx, 7; unsigned int
0x18000e954  call    ?getMaxBits@CInputBitStream@@QEAAEKPEAE@Z; CInputBitStream::getMaxBits(ulong,uchar *)
0x18000e959  mov     rcx, [rbx+890h]; this
0x18000e960  cmp     dword ptr [rcx+14h], 0
0x18000e964  jnz     loc_18000EB5B
0x18000e96a  test    al, al
0x18000e96c  jz      short loc_18000E9B8
0x18000e96e  movzx   ebp, al
0x18000e971  mov     edx, ebp; unsigned int
0x18000e973  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000e978  mov     rcx, [rbx+890h]
0x18000e97f  cmp     dword ptr [rcx+14h], 0
0x18000e983  jnz     loc_18000EB5B
0x18000e989  mov     r8d, [rbx+140h]
0x18000e990  lea     ecx, [rbp-1]
0x18000e993  movzx   edx, al
0x18000e996  movzx   eax, cl
0x18000e999  bt      edx, eax
0x18000e99c  jnb     short loc_18000E9A4
0x18000e99e  lea     eax, [rdx+r8]
0x18000e9a2  jmp     short loc_18000E9B2
0x18000e9a4  mov     ecx, ebp
0x18000e9a6  mov     eax, esi
0x18000e9a8  shl     eax, cl
0x18000e9aa  sub     edx, eax
0x18000e9ac  lea     eax, [r8+1]
0x18000e9b0  add     eax, edx
0x18000e9b2  mov     [rbx+140h], eax
0x18000e9b8  mov     eax, [rbx+16Ch]
0x18000e9be  mov     r9, r14; unsigned __int8 *
0x18000e9c1  imul    eax, [rbx+140h]
0x18000e9c8  mov     rdx, r12; struct CDCTTableInfo_Dec *
0x18000e9cb  mov     rcx, rbx; this
0x18000e9ce  mov     [rbx+650h], eax
0x18000e9d4  mov     eax, [rbx+150h]
0x18000e9da  mov     r8d, [r15+rdi*4]; int
0x18000e9de  mov     [rsp+78h+var_58], eax; int
0x18000e9e2  call    ?decodeIntraBlock@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@JPEAEJ@Z; CVideoObjectDecoder::decodeIntraBlock(CDCTTableInfo_Dec *,long,uchar *,long)
0x18000e9e7  test    eax, eax
0x18000e9e9  jnz     loc_18000EB60
0x18000e9ef  mov     eax, 8
0x18000e9f4  cmp     edi, esi
0x18000e9f6  jnz     short loc_18000E9FE
0x18000e9f8  mov     eax, [rbx+0E70h]
0x18000e9fe  add     edi, esi
0x18000ea00  cmp     edi, 4
0x18000ea03  jnb     short loc_18000EA0F
0x18000ea05  cdqe
0x18000ea07  add     r14, rax
0x18000ea0a  jmp     loc_18000E941
0x18000ea0f  mov     rcx, [rbx+890h]; this
0x18000ea16  lea     r8, ?gDecodeCodeTableIntraDCc@@3PAEA; unsigned __int8 *
0x18000ea1d  mov     edx, 8; unsigned int
0x18000ea22  call    ?getMaxBits@CInputBitStream@@QEAAEKPEAE@Z; CInputBitStream::getMaxBits(ulong,uchar *)
0x18000ea27  mov     rcx, [rbx+890h]; this
0x18000ea2e  cmp     dword ptr [rcx+14h], 0
0x18000ea32  jnz     loc_18000EB5B
0x18000ea38  test    al, al
0x18000ea3a  jz      short loc_18000EA86
0x18000ea3c  movzx   edi, al
0x18000ea3f  mov     edx, edi; unsigned int
0x18000ea41  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ea46  mov     rcx, [rbx+890h]
0x18000ea4d  cmp     dword ptr [rcx+14h], 0
0x18000ea51  jnz     loc_18000EB5B
0x18000ea57  mov     r8d, [rbx+144h]
0x18000ea5e  lea     ecx, [rdi-1]
0x18000ea61  movzx   edx, al
0x18000ea64  movzx   eax, cl
0x18000ea67  bt      edx, eax
0x18000ea6a  jnb     short loc_18000EA72
0x18000ea6c  lea     eax, [rdx+r8]
0x18000ea70  jmp     short loc_18000EA80
0x18000ea72  mov     ecx, edi
0x18000ea74  mov     eax, esi
0x18000ea76  shl     eax, cl
0x18000ea78  sub     edx, eax
0x18000ea7a  lea     eax, [r8+1]
0x18000ea7e  add     eax, edx
0x18000ea80  mov     [rbx+144h], eax
0x18000ea86  mov     eax, [rbx+144h]
0x18000ea8c  mov     rdx, r13; struct CDCTTableInfo_Dec *
0x18000ea8f  mov     r9, [rsp+78h+arg_18]; unsigned __int8 *
0x18000ea97  mov     rcx, rbx; this
0x18000ea9a  shl     eax, 3
0x18000ea9d  mov     [rbx+650h], eax
0x18000eaa3  mov     eax, [rbx+154h]
0x18000eaa9  mov     r8d, [r15+10h]; int
0x18000eaad  mov     [rsp+78h+var_58], eax; int
0x18000eab1  call    ?decodeIntraBlock@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@JPEAEJ@Z; CVideoObjectDecoder::decodeIntraBlock(CDCTTableInfo_Dec *,long,uchar *,long)
0x18000eab6  test    eax, eax
0x18000eab8  jnz     loc_18000EB60
0x18000eabe  mov     rcx, [rbx+890h]; this
0x18000eac5  lea     r8, ?gDecodeCodeTableIntraDCc@@3PAEA; unsigned __int8 *
0x18000eacc  lea     edx, [rax+8]; unsigned int
0x18000eacf  call    ?getMaxBits@CInputBitStream@@QEAAEKPEAE@Z; CInputBitStream::getMaxBits(ulong,uchar *)
0x18000ead4  mov     rcx, [rbx+890h]; this
0x18000eadb  cmp     dword ptr [rcx+14h], 0
0x18000eadf  jnz     short loc_18000EB5B
0x18000eae1  test    al, al
0x18000eae3  jz      short loc_18000EB29
0x18000eae5  movzx   edi, al
0x18000eae8  mov     edx, edi; unsigned int
0x18000eaea  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000eaef  mov     rcx, [rbx+890h]
0x18000eaf6  cmp     dword ptr [rcx+14h], 0
0x18000eafa  jnz     short loc_18000EB5B
0x18000eafc  mov     r8d, [rbx+148h]
0x18000eb03  lea     ecx, [rdi-1]
0x18000eb06  movzx   edx, al
0x18000eb09  movzx   eax, cl
0x18000eb0c  bt      edx, eax
0x18000eb0f  jnb     short loc_18000EB17
0x18000eb11  lea     eax, [rdx+r8]
0x18000eb15  jmp     short loc_18000EB23
0x18000eb17  mov     ecx, edi
0x18000eb19  lea     eax, [r8+1]
0x18000eb1d  shl     esi, cl
0x18000eb1f  sub     edx, esi
0x18000eb21  add     eax, edx
0x18000eb23  mov     [rbx+148h], eax
0x18000eb29  mov     eax, [rbx+148h]
0x18000eb2f  mov     rdx, r13; struct CDCTTableInfo_Dec *
0x18000eb32  mov     r9, [rsp+78h+arg_20]; unsigned __int8 *
0x18000eb3a  mov     rcx, rbx; this
0x18000eb3d  shl     eax, 3
0x18000eb40  mov     [rbx+650h], eax
0x18000eb46  mov     eax, [rbx+154h]
0x18000eb4c  mov     r8d, [r15+14h]; int
0x18000eb50  mov     [rsp+78h+var_58], eax; int
0x18000eb54  call    ?decodeIntraBlock@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@JPEAEJ@Z; CVideoObjectDecoder::decodeIntraBlock(CDCTTableInfo_Dec *,long,uchar *,long)
0x18000eb59  jmp     short loc_18000EB60
0x18000eb5b  mov     eax, 0FFFFFF9Ch
0x18000eb60  add     rsp, 38h
0x18000eb64  pop     r15
0x18000eb66  pop     r14
0x18000eb68  pop     r13
0x18000eb6a  pop     r12
0x18000eb6c  pop     rdi
0x18000eb6d  pop     rsi
0x18000eb6e  pop     rbp
0x18000eb6f  pop     rbx
0x18000eb70  retn
```
