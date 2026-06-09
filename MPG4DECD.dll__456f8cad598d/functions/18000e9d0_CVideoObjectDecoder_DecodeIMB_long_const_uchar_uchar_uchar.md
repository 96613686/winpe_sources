# CVideoObjectDecoder::DecodeIMB(long const *,uchar *,uchar *,uchar *)

- ea: `0x18000e9d0`
- end: `0x18000ec31`
- name: `?DecodeIMB@CVideoObjectDecoder@@AEAAJPEBJPEAE11@Z`
- size: `609`
- prototype: `__int64 __usercall@<rax>(CVideoObjectDecoder *__hidden this@<rcx>, const int *@<rdx>, unsigned __int8 *@<r8>, unsigned __int8 *@<r9>, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f500`
- `0x18000fa90`
- `0x1800106c0`
- `0x180011040`

## callees

- `0x18000b16c`
- `0x18000d744`
- `0x18000dd4c`
- `0x18000e9d0`

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
    result = CVideoObjectDecoder::decodeIntraBlock((void **)this, v7, a2[v6], a3, *((_DWORD *)this + 84));
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
    result = CVideoObjectDecoder::decodeIntraBlock((void **)this, v5, a2[4], a4, *((_DWORD *)this + 85));
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
        return CVideoObjectDecoder::decodeIntraBlock((void **)this, v5, a2[5], a5, *((_DWORD *)this + 85));
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
0x18000e9d0  mov     [rsp+arg_18], r9
0x18000e9d5  push    rbx
0x18000e9d6  push    rbp
0x18000e9d7  push    rsi
0x18000e9d8  push    rdi
0x18000e9d9  push    r12
0x18000e9db  push    r13
0x18000e9dd  push    r14
0x18000e9df  push    r15
0x18000e9e1  sub     rsp, 38h
0x18000e9e5  mov     r13, [rcx+0DB8h]
0x18000e9ec  xor     edi, edi
0x18000e9ee  mov     r12, [rcx+0DC0h]
0x18000e9f5  mov     r14, r8
0x18000e9f8  mov     r15, rdx
0x18000e9fb  mov     rbx, rcx
0x18000e9fe  lea     esi, [rdi+1]
0x18000ea01  mov     rcx, [rbx+890h]; this
0x18000ea08  lea     r8, ?gDecodeCodeTableIntraDCy@@3PAEA; unsigned __int8 *
0x18000ea0f  mov     edx, 7; unsigned int
0x18000ea14  call    ?getMaxBits@CInputBitStream@@QEAAEKPEAE@Z; CInputBitStream::getMaxBits(ulong,uchar *)
0x18000ea19  mov     rcx, [rbx+890h]; this
0x18000ea20  cmp     dword ptr [rcx+14h], 0
0x18000ea24  jnz     loc_18000EC1B
0x18000ea2a  test    al, al
0x18000ea2c  jz      short loc_18000EA78
0x18000ea2e  movzx   ebp, al
0x18000ea31  mov     edx, ebp; unsigned int
0x18000ea33  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ea38  mov     rcx, [rbx+890h]
0x18000ea3f  cmp     dword ptr [rcx+14h], 0
0x18000ea43  jnz     loc_18000EC1B
0x18000ea49  mov     r8d, [rbx+140h]
0x18000ea50  lea     ecx, [rbp-1]
0x18000ea53  movzx   edx, al
0x18000ea56  movzx   eax, cl
0x18000ea59  bt      edx, eax
0x18000ea5c  jnb     short loc_18000EA64
0x18000ea5e  lea     eax, [rdx+r8]
0x18000ea62  jmp     short loc_18000EA72
0x18000ea64  mov     ecx, ebp
0x18000ea66  mov     eax, esi
0x18000ea68  shl     eax, cl
0x18000ea6a  sub     edx, eax
0x18000ea6c  lea     eax, [r8+1]
0x18000ea70  add     eax, edx
0x18000ea72  mov     [rbx+140h], eax
0x18000ea78  mov     eax, [rbx+16Ch]
0x18000ea7e  mov     r9, r14; unsigned __int8 *
0x18000ea81  imul    eax, [rbx+140h]
0x18000ea88  mov     rdx, r12; struct CDCTTableInfo_Dec *
0x18000ea8b  mov     rcx, rbx; this
0x18000ea8e  mov     [rbx+650h], eax
0x18000ea94  mov     eax, [rbx+150h]
0x18000ea9a  mov     r8d, [r15+rdi*4]; int
0x18000ea9e  mov     [rsp+78h+var_58], eax; int
0x18000eaa2  call    ?decodeIntraBlock@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@JPEAEJ@Z; CVideoObjectDecoder::decodeIntraBlock(CDCTTableInfo_Dec *,long,uchar *,long)
0x18000eaa7  test    eax, eax
0x18000eaa9  jnz     loc_18000EC20
0x18000eaaf  mov     eax, 8
0x18000eab4  cmp     edi, esi
0x18000eab6  jnz     short loc_18000EABE
0x18000eab8  mov     eax, [rbx+0E70h]
0x18000eabe  add     edi, esi
0x18000eac0  cmp     edi, 4
0x18000eac3  jnb     short loc_18000EACF
0x18000eac5  cdqe
0x18000eac7  add     r14, rax
0x18000eaca  jmp     loc_18000EA01
0x18000eacf  mov     rcx, [rbx+890h]; this
0x18000ead6  lea     r8, ?gDecodeCodeTableIntraDCc@@3PAEA; unsigned __int8 *
0x18000eadd  mov     edx, 8; unsigned int
0x18000eae2  call    ?getMaxBits@CInputBitStream@@QEAAEKPEAE@Z; CInputBitStream::getMaxBits(ulong,uchar *)
0x18000eae7  mov     rcx, [rbx+890h]; this
0x18000eaee  cmp     dword ptr [rcx+14h], 0
0x18000eaf2  jnz     loc_18000EC1B
0x18000eaf8  test    al, al
0x18000eafa  jz      short loc_18000EB46
0x18000eafc  movzx   edi, al
0x18000eaff  mov     edx, edi; unsigned int
0x18000eb01  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000eb06  mov     rcx, [rbx+890h]
0x18000eb0d  cmp     dword ptr [rcx+14h], 0
0x18000eb11  jnz     loc_18000EC1B
0x18000eb17  mov     r8d, [rbx+144h]
0x18000eb1e  lea     ecx, [rdi-1]
0x18000eb21  movzx   edx, al
0x18000eb24  movzx   eax, cl
0x18000eb27  bt      edx, eax
0x18000eb2a  jnb     short loc_18000EB32
0x18000eb2c  lea     eax, [rdx+r8]
0x18000eb30  jmp     short loc_18000EB40
0x18000eb32  mov     ecx, edi
0x18000eb34  mov     eax, esi
0x18000eb36  shl     eax, cl
0x18000eb38  sub     edx, eax
0x18000eb3a  lea     eax, [r8+1]
0x18000eb3e  add     eax, edx
0x18000eb40  mov     [rbx+144h], eax
0x18000eb46  mov     eax, [rbx+144h]
0x18000eb4c  mov     rdx, r13; struct CDCTTableInfo_Dec *
0x18000eb4f  mov     r9, [rsp+78h+arg_18]; unsigned __int8 *
0x18000eb57  mov     rcx, rbx; this
0x18000eb5a  shl     eax, 3
0x18000eb5d  mov     [rbx+650h], eax
0x18000eb63  mov     eax, [rbx+154h]
0x18000eb69  mov     r8d, [r15+10h]; int
0x18000eb6d  mov     [rsp+78h+var_58], eax; int
0x18000eb71  call    ?decodeIntraBlock@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@JPEAEJ@Z; CVideoObjectDecoder::decodeIntraBlock(CDCTTableInfo_Dec *,long,uchar *,long)
0x18000eb76  test    eax, eax
0x18000eb78  jnz     loc_18000EC20
0x18000eb7e  mov     rcx, [rbx+890h]; this
0x18000eb85  lea     r8, ?gDecodeCodeTableIntraDCc@@3PAEA; unsigned __int8 *
0x18000eb8c  lea     edx, [rax+8]; unsigned int
0x18000eb8f  call    ?getMaxBits@CInputBitStream@@QEAAEKPEAE@Z; CInputBitStream::getMaxBits(ulong,uchar *)
0x18000eb94  mov     rcx, [rbx+890h]; this
0x18000eb9b  cmp     dword ptr [rcx+14h], 0
0x18000eb9f  jnz     short loc_18000EC1B
0x18000eba1  test    al, al
0x18000eba3  jz      short loc_18000EBE9
0x18000eba5  movzx   edi, al
0x18000eba8  mov     edx, edi; unsigned int
0x18000ebaa  call    ?getBits@CInputBitStream@@QEAAKK@Z; CInputBitStream::getBits(ulong)
0x18000ebaf  mov     rcx, [rbx+890h]
0x18000ebb6  cmp     dword ptr [rcx+14h], 0
0x18000ebba  jnz     short loc_18000EC1B
0x18000ebbc  mov     r8d, [rbx+148h]
0x18000ebc3  lea     ecx, [rdi-1]
0x18000ebc6  movzx   edx, al
0x18000ebc9  movzx   eax, cl
0x18000ebcc  bt      edx, eax
0x18000ebcf  jnb     short loc_18000EBD7
0x18000ebd1  lea     eax, [rdx+r8]
0x18000ebd5  jmp     short loc_18000EBE3
0x18000ebd7  mov     ecx, edi
0x18000ebd9  lea     eax, [r8+1]
0x18000ebdd  shl     esi, cl
0x18000ebdf  sub     edx, esi
0x18000ebe1  add     eax, edx
0x18000ebe3  mov     [rbx+148h], eax
0x18000ebe9  mov     eax, [rbx+148h]
0x18000ebef  mov     rdx, r13; struct CDCTTableInfo_Dec *
0x18000ebf2  mov     r9, [rsp+78h+arg_20]; unsigned __int8 *
0x18000ebfa  mov     rcx, rbx; this
0x18000ebfd  shl     eax, 3
0x18000ec00  mov     [rbx+650h], eax
0x18000ec06  mov     eax, [rbx+154h]
0x18000ec0c  mov     r8d, [r15+14h]; int
0x18000ec10  mov     [rsp+78h+var_58], eax; int
0x18000ec14  call    ?decodeIntraBlock@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@JPEAEJ@Z; CVideoObjectDecoder::decodeIntraBlock(CDCTTableInfo_Dec *,long,uchar *,long)
0x18000ec19  jmp     short loc_18000EC20
0x18000ec1b  mov     eax, 0FFFFFF9Ch
0x18000ec20  add     rsp, 38h
0x18000ec24  pop     r15
0x18000ec26  pop     r14
0x18000ec28  pop     r13
0x18000ec2a  pop     r12
0x18000ec2c  pop     rdi
0x18000ec2d  pop     rsi
0x18000ec2e  pop     rbp
0x18000ec2f  pop     rbx
0x18000ec30  retn
```
