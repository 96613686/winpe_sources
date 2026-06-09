# GenADTG::SaveColumnDescriptor(ushort,ushort)

- ea: `0x180007968`
- end: `0x180007fda`
- name: `?SaveColumnDescriptor@GenADTG@@QEAAHGG@Z`
- size: `1650`
- prototype: `__int64 __fastcall(GenADTG *__hidden this, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x1800091a4`

## callees

- `0x18000261c`
- `0x180002cd4`
- `0x180002d18`
- `0x180002d60`
- `0x180002da8`
- `0x180002e38`
- `0x180002e7c`
- `0x180003abc`
- `0x180004038`
- `0x1800040a8`
- `0x1800040e8`
- `0x18000412c`
- `0x18000416c`
- `0x1800041ac`
- `0x1800041f8`
- `0x180007968`
- `0x18000924c`
- `0x180009490`
- `0x1800096e8`
- `0x18002ccd0`

## pseudocode

```c
__int64 __fastcall GenADTG::SaveColumnDescriptor(GenADTG *this, unsigned __int16 a2, __int16 a3)
{
  __int64 v3; // rsi
  CMetaData *v4; // r14
  __int64 v6; // rdi
  CMetaData *v7; // rcx
  unsigned __int16 v8; // dx
  unsigned __int16 v9; // dx
  int Precision; // r13d
  unsigned __int16 v11; // dx
  unsigned __int16 v12; // dx
  unsigned int Flags; // eax
  unsigned __int16 v14; // dx
  const unsigned __int16 *v15; // r10
  __int16 v16; // r11
  const unsigned __int16 *v17; // r15
  __int64 v19; // rcx
  __int16 v20; // r9
  unsigned __int16 *BaseColumnName; // rax
  __int16 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // rax
  __int16 v25; // r11
  unsigned __int16 v26; // r10
  unsigned __int16 v27; // ax
  __int16 RelationConditionsSize; // ax
  __int16 v29; // r10
  __int64 v30; // rax
  const unsigned __int16 *v31; // rdx
  const unsigned __int16 *BaseCatalogName; // rax
  const unsigned __int16 *BaseSchemaName; // rax
  __int64 v34; // rcx
  __int64 v35; // rdi
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rdi
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rax
  const unsigned __int8 *RelationConditions; // rax
  const unsigned __int8 *CalculationInfo; // rax
  unsigned __int16 v50[2]; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int8 v51[4]; // [rsp+24h] [rbp-2Ch] BYREF
  unsigned __int8 v52; // [rsp+28h] [rbp-28h] BYREF
  __int16 v53; // [rsp+29h] [rbp-27h]
  unsigned __int8 v54[4]; // [rsp+2Ch] [rbp-24h] BYREF
  unsigned __int8 v55[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 v56[4]; // [rsp+34h] [rbp-1Ch] BYREF
  unsigned __int8 v57[4]; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 v58[4]; // [rsp+3Ch] [rbp-14h] BYREF
  unsigned __int8 v59[4]; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int8 v60[12]; // [rsp+44h] [rbp-Ch] BYREF
  unsigned __int8 v61; // [rsp+90h] [rbp+40h] BYREF
  __int16 v62; // [rsp+A0h] [rbp+50h] BYREF
  int v63; // [rsp+A8h] [rbp+58h] BYREF

  v62 = a3;
  v3 = a2;
  v61 = 6;
  v4 = (GenADTG *)((char *)this + 128);
  v50[0] = 25;
  *(_DWORD *)v60 = 0;
  v6 = -1;
  *(_DWORD *)v59 = 0;
  *(_WORD *)v55 = -1;
  *(_DWORD *)v54 = 0;
  CMetaData::mdGetName((GenADTG *)((char *)this + 128), a2);
  *(_WORD *)v51 = CMetaData::mdGetType(v7, v3);
  *(_DWORD *)v58 = CMetaData::mdGetSize(v4, v8);
  Precision = CMetaData::mdGetPrecision(v4, v9);
  LOBYTE(v63) = CMetaData::mdGetScale(v4, v11);
  Flags = CMetaData::mdGetFlags(v4, v12);
  *(_DWORD *)v56 = Flags;
  v17 = (const unsigned __int16 *)&dword_1800362F4;
  if ( v15 )
    v17 = v15;
  if ( *((_DWORD *)this + 50) && ((Flags & 0x2000) != 0 || v16 == 136) )
    return 0;
  v19 = *((_QWORD *)this + 21);
  v53 = 0;
  v52 = 0x80;
  if ( v19 && *(_WORD *)(v19 + 4 * v3 + 2) )
  {
    v52 = -16;
    v50[0] = 31;
    if ( CMetaData::mdGetBaseColumnName(v4, v14) )
    {
      BaseColumnName = CMetaData::mdGetBaseColumnName(v4, v3);
      v23 = -1;
      do
        ++v23;
      while ( BaseColumnName[v23] );
      v50[0] = v22 + 2 * v23;
    }
    else
    {
      v24 = -1;
      do
        ++v24;
      while ( v17[v24] );
      v50[0] = v20 + 2 * v24;
    }
  }
  GenADTG::SetOptionalColumnsMap(this, v3, &v52, v50);
  do
    ++v6;
  while ( v17[v6] );
  v25 = 4;
  v26 = v50[0] + 2 * (v6 + 1);
  v50[0] = v26;
  if ( *((_DWORD *)this + 71) != 1 )
  {
    v26 += 4;
    v50[0] = v26;
  }
  v27 = v26;
  if ( ((*(_WORD *)v56 & 0x2000) != 0 || *(_WORD *)v51 == 136) && !*((_DWORD *)this + 50) )
  {
    v50[0] = v26 + 4;
    RelationConditionsSize = CMetaData::mdGetRelationConditionsSize(v4, v3);
    v27 = v25 + v29 + RelationConditionsSize;
    v50[0] = v27;
  }
  if ( ((unsigned __int8)v25 & HIBYTE(v53)) != 0 )
    v50[0] = v25 + v27;
  GenADTG::SaveToBuffer(this, &v61, 1u);
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)v50, 2u);
  GenADTG::SaveToBuffer(this, &v52, 3u);
  GenADTG::SaveToBuffer(this, (const unsigned __int8 *)&v62, 2u);
  GenADTG::SaveString(this, v17);
  v30 = *((_QWORD *)this + 21);
  if ( v30 && *(_WORD *)(v30 + 4 * v3 + 2) )
  {
    GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(*((_QWORD *)v4 + 5) + 4 * v3), 2u);
    GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(*((_QWORD *)this + 21) + 2LL + 4 * v3), 2u);
    if ( CMetaData::mdGetBaseColumnName(v4, v3) )
      v31 = CMetaData::mdGetBaseColumnName(v4, v3);
    else
      v31 = v17;
    GenADTG::SaveString(this, v31);
  }
  GenADTG::SaveToBuffer(this, v51, 2u);
  GenADTG::SaveToBuffer(this, v58, 4u);
  *(_DWORD *)v59 = Precision;
  GenADTG::SaveToBuffer(this, v59, 4u);
  *(_DWORD *)v60 = (unsigned __int8)v63;
  GenADTG::SaveToBuffer(this, v60, 4u);
  GenADTG::SaveToBuffer(this, v56, 4u);
  if ( CMetaData::mdGetBaseCatalogName(v4, v3) )
  {
    BaseCatalogName = CMetaData::mdGetBaseCatalogName(v4, v3);
    GenADTG::SaveString(this, BaseCatalogName);
  }
  if ( CMetaData::mdGetBaseSchemaName(v4, v3) )
  {
    BaseSchemaName = CMetaData::mdGetBaseSchemaName(v4, v3);
    GenADTG::SaveString(this, BaseSchemaName);
  }
  v34 = *((_QWORD *)this + 20);
  if ( v34 )
  {
    v35 = 9648 * v3;
    if ( !*(_DWORD *)(9648 * v3 + v34 + 6364) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v35 + v34 + 6360), 4u);
    v36 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v36 + v35 + 6356) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v35 + v36 + 6352), 4u);
    v37 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v37 + v35 + 6372) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v35 + v37 + 6368), 4u);
    v38 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v38 + v35 + 6400) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v35 + v38 + 6376), 0x18u);
    v39 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v39 + v35 + 7432) )
      GenADTG::SaveString(this, (const unsigned __int16 *)(v35 + v39 + 6404));
    v40 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v40 + v35 + 8476) )
      GenADTG::SaveString(this, (const unsigned __int16 *)(v35 + v40 + 7448));
    v41 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v41 + v35 + 9516) )
      GenADTG::SaveString(this, (const unsigned __int16 *)(v35 + v41 + 8488));
  }
  *(_WORD *)v57 = CMetaData::mdGetAutoIncrement(v4, v3);
  GenADTG::SaveToBuffer(this, v57, 2u);
  v42 = *((_QWORD *)this + 20);
  if ( v42 )
  {
    v43 = 9648 * v3;
    if ( !*(_DWORD *)(9648 * v3 + v42 + 9540) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v43 + v42 + 9536), 2u);
    v44 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v44 + v43 + 9548) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v43 + v44 + 9544), 4u);
    v45 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v45 + v43 + 9556) )
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)(v43 + v45 + 9552), 2u);
    v46 = *((_QWORD *)this + 20);
    if ( !*(_DWORD *)(v46 + v43 + 9568) )
    {
      v63 = 0;
      v63 = DownsizeToULONGThrow<unsigned __int64>(*(_QWORD *)(v46 + v43 + 9560));
      GenADTG::SaveToBuffer(this, (const unsigned __int8 *)&v63, 4u);
    }
    v47 = *((_QWORD *)this + 20);
    if ( *(_DWORD *)(v47 + v43 + 2160)
      || !(unsigned int)IsSame((const struct _GUID *)(v43 + v47 + 2144), &DBCOL_SPECIALCOL) )
    {
      goto LABEL_65;
    }
    goto LABEL_64;
  }
  if ( (unsigned __int16)v3 >= *((_WORD *)this + 65) )
LABEL_64:
    *(_WORD *)v55 = 0;
LABEL_65:
  GenADTG::SaveToBuffer(this, v55, 2u);
  if ( *((_DWORD *)this + 71) != 1 )
    GenADTG::SaveToBuffer(this, (const unsigned __int8 *)this + 284, 4u);
  if ( ((*(_WORD *)v56 & 0x2000) != 0 || *(_WORD *)v51 == 136) && !*((_DWORD *)this + 50) )
  {
    *(_DWORD *)v54 = CMetaData::mdGetRelationConditionsSize(v4, v3);
    GenADTG::SaveToBuffer(this, v54, 4u);
    RelationConditions = CMetaData::mdGetRelationConditions(v4, v3);
    GenADTG::SaveToBuffer(this, RelationConditions, *(unsigned int *)v54);
    *(_DWORD *)v54 = 0;
    GenADTG::SaveToBuffer(this, v54, 4u);
  }
  if ( (v53 & 0x400) != 0 )
  {
    *(_DWORD *)v54 = CMetaData::mdGetCalculationInfoSize(v4, v3);
    GenADTG::SaveToBuffer(this, v54, 4u);
    CalculationInfo = CMetaData::mdGetCalculationInfo(v4, v3);
    GenADTG::SaveToBuffer(this, CalculationInfo, *(unsigned int *)v54);
  }
  return 1;
}

```

## disassembly

```asm
0x180007968  mov     [rsp-38h+arg_8], rbx
0x18000796d  mov     [rsp-38h+arg_10], r8w
0x180007973  push    rbp
0x180007974  push    rsi
0x180007975  push    rdi
0x180007976  push    r12
0x180007978  push    r13
0x18000797a  push    r14
0x18000797c  push    r15
0x18000797e  mov     rbp, rsp
0x180007981  sub     rsp, 50h
0x180007985  xor     r12d, r12d
0x180007988  movzx   esi, dx
0x18000798b  mov     eax, 19h
0x180007990  mov     [rbp+arg_0], 6
0x180007994  lea     r14, [rcx+80h]
0x18000799b  mov     [rbp+var_30], ax
0x18000799f  mov     rbx, rcx
0x1800079a2  mov     dword ptr [rbp+var_C], r12d
0x1800079a6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800079aa  mov     dword ptr [rbp+var_10], r12d
0x1800079ae  movzx   edx, si; unsigned __int16
0x1800079b1  mov     word ptr [rbp+var_20], di
0x1800079b5  mov     rcx, r14; this
0x1800079b8  mov     dword ptr [rbp+var_1C], r12d
0x1800079bc  mov     dword ptr [rbp+var_14], r12d
0x1800079c0  mov     word ptr [rbp+var_2C], r12w
0x1800079c5  mov     dword ptr [rbp+var_24], r12d
0x1800079c9  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x1800079ce  movzx   edx, si; unsigned __int16
0x1800079d1  mov     r10, rax
0x1800079d4  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x1800079d9  mov     rcx, r14; this
0x1800079dc  mov     word ptr [rbp+var_2C], ax
0x1800079e0  movzx   r11d, ax
0x1800079e4  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x1800079e9  mov     rcx, r14; this
0x1800079ec  mov     dword ptr [rbp+var_14], eax
0x1800079ef  call    ?mdGetPrecision@CMetaData@@QEAAEG@Z; CMetaData::mdGetPrecision(ushort)
0x1800079f4  mov     rcx, r14; this
0x1800079f7  movzx   r13d, al
0x1800079fb  call    ?mdGetScale@CMetaData@@QEAAEG@Z; CMetaData::mdGetScale(ushort)
0x180007a00  mov     rcx, r14; this
0x180007a03  mov     byte ptr [rbp+arg_18], al
0x180007a06  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x180007a0b  test    r10, r10
0x180007a0e  mov     dword ptr [rbp+var_1C], eax
0x180007a11  lea     r15, dword_1800362F4
0x180007a18  mov     ecx, 88h
0x180007a1d  cmovnz  r15, r10
0x180007a21  cmp     [rbx+0C8h], r12d
0x180007a28  jz      short loc_180007A3D
0x180007a2a  bt      eax, 0Dh
0x180007a2e  jb      short loc_180007A36
0x180007a30  cmp     r11w, cx
0x180007a34  jnz     short loc_180007A3D
0x180007a36  xor     eax, eax
0x180007a38  jmp     loc_180007FC2
0x180007a3d  mov     rcx, [rbx+0A8h]
0x180007a44  mov     [rbp+var_27], r12w
0x180007a49  mov     [rbp+var_28], 80h
0x180007a4d  test    rcx, rcx
0x180007a50  jz      short loc_180007AB3
0x180007a52  cmp     [rcx+rsi*4+2], r12w
0x180007a58  jz      short loc_180007AB3
0x180007a5a  mov     r9d, 1Fh
0x180007a60  mov     [rbp+var_28], 0F0h
0x180007a64  mov     rcx, r14; this
0x180007a67  mov     [rbp+var_30], r9w
0x180007a6c  call    ?mdGetBaseColumnName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseColumnName(ushort)
0x180007a71  test    rax, rax
0x180007a74  jz      short loc_180007A9B
0x180007a76  movzx   edx, si; unsigned __int16
0x180007a79  mov     rcx, r14; this
0x180007a7c  call    ?mdGetBaseColumnName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseColumnName(ushort)
0x180007a81  mov     rcx, rdi
0x180007a84  inc     rcx
0x180007a87  cmp     [rax+rcx*2], r12w
0x180007a8c  jnz     short loc_180007A84
0x180007a8e  add     cx, cx
0x180007a91  add     cx, r9w
0x180007a95  mov     [rbp+var_30], cx
0x180007a99  jmp     short loc_180007AB3
0x180007a9b  mov     rax, rdi
0x180007a9e  inc     rax
0x180007aa1  cmp     [r15+rax*2], r12w
0x180007aa6  jnz     short loc_180007A9E
0x180007aa8  add     ax, ax
0x180007aab  add     ax, r9w
0x180007aaf  mov     [rbp+var_30], ax
0x180007ab3  lea     r9, [rbp+var_30]; unsigned __int16 *
0x180007ab7  movzx   edx, si; unsigned __int16
0x180007aba  lea     r8, [rbp+var_28]; unsigned __int8 *
0x180007abe  mov     rcx, rbx; this
0x180007ac1  call    ?SetOptionalColumnsMap@GenADTG@@AEAAXGPEAEPEAG@Z; GenADTG::SetOptionalColumnsMap(ushort,uchar *,ushort *)
0x180007ac6  inc     rdi
0x180007ac9  cmp     [r15+rdi*2], r12w
0x180007ace  jnz     short loc_180007AC6
0x180007ad0  mov     ecx, 1
0x180007ad5  lea     r12, [rbx+11Ch]
0x180007adc  add     di, cx
0x180007adf  lea     r11d, [rcx+3]
0x180007ae3  lea     r10d, [rdi+rdi]
0x180007ae7  add     r10w, [rbp+var_30]
0x180007aec  mov     [rbp+var_30], r10w
0x180007af1  cmp     [r12], ecx
0x180007af5  jz      short loc_180007B00
0x180007af7  add     r10w, r11w
0x180007afb  mov     [rbp+var_30], r10w
0x180007b00  test    dword ptr [rbp+var_1C], 2000h
0x180007b07  movzx   eax, r10w
0x180007b0b  jnz     short loc_180007B18
0x180007b0d  mov     edx, 88h
0x180007b12  cmp     word ptr [rbp+var_2C], dx
0x180007b16  jnz     short loc_180007B46
0x180007b18  cmp     dword ptr [rbx+0C8h], 0
0x180007b1f  jnz     short loc_180007B46
0x180007b21  add     r10w, r11w
0x180007b25  movzx   edx, si; unsigned __int16
0x180007b28  mov     rcx, r14; this
0x180007b2b  mov     [rbp+var_30], r10w
0x180007b30  call    ?mdGetRelationConditionsSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetRelationConditionsSize(ushort)
0x180007b35  add     ax, r10w
0x180007b39  mov     ecx, 1
0x180007b3e  add     ax, r11w
0x180007b42  mov     [rbp+var_30], ax
0x180007b46  test    byte ptr [rbp+var_27+1], r11b
0x180007b4a  jz      short loc_180007B54
0x180007b4c  add     ax, r11w
0x180007b50  mov     [rbp+var_30], ax
0x180007b54  mov     r8d, ecx; unsigned int
0x180007b57  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x180007b5b  mov     rcx, rbx; this
0x180007b5e  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007b63  mov     r8d, 2; unsigned int
0x180007b69  lea     rdx, [rbp+var_30]; unsigned __int8 *
0x180007b6d  mov     rcx, rbx; this
0x180007b70  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007b75  mov     r8d, 3; unsigned int
0x180007b7b  lea     rdx, [rbp+var_28]; unsigned __int8 *
0x180007b7f  mov     rcx, rbx; this
0x180007b82  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007b87  mov     r8d, 2; unsigned int
0x180007b8d  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x180007b91  mov     rcx, rbx; this
0x180007b94  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007b99  mov     rdx, r15; unsigned __int16 *
0x180007b9c  mov     rcx, rbx; this
0x180007b9f  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007ba4  mov     rax, [rbx+0A8h]
0x180007bab  xor     ecx, ecx
0x180007bad  test    rax, rax
0x180007bb0  jz      short loc_180007C15
0x180007bb2  cmp     [rax+rsi*4+2], cx
0x180007bb7  jz      short loc_180007C15
0x180007bb9  mov     rax, [r14+28h]
0x180007bbd  lea     r8d, [rcx+2]; unsigned int
0x180007bc1  mov     rcx, rbx; this
0x180007bc4  lea     rdx, [rax+rsi*4]; unsigned __int8 *
0x180007bc8  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007bcd  mov     rdx, [rbx+0A8h]
0x180007bd4  mov     r8d, 2; unsigned int
0x180007bda  add     rdx, 2
0x180007bde  mov     rcx, rbx; this
0x180007be1  lea     rdx, [rdx+rsi*4]; unsigned __int8 *
0x180007be5  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007bea  movzx   edx, si; unsigned __int16
0x180007bed  mov     rcx, r14; this
0x180007bf0  call    ?mdGetBaseColumnName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseColumnName(ushort)
0x180007bf5  test    rax, rax
0x180007bf8  jz      short loc_180007C0A
0x180007bfa  movzx   edx, si; unsigned __int16
0x180007bfd  mov     rcx, r14; this
0x180007c00  call    ?mdGetBaseColumnName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseColumnName(ushort)
0x180007c05  mov     rdx, rax
0x180007c08  jmp     short loc_180007C0D
0x180007c0a  mov     rdx, r15; unsigned __int16 *
0x180007c0d  mov     rcx, rbx; this
0x180007c10  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007c15  mov     r8d, 2; unsigned int
0x180007c1b  lea     rdx, [rbp+var_2C]; unsigned __int8 *
0x180007c1f  mov     rcx, rbx; this
0x180007c22  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007c27  mov     r8d, 4; unsigned int
0x180007c2d  lea     rdx, [rbp+var_14]; unsigned __int8 *
0x180007c31  mov     rcx, rbx; this
0x180007c34  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007c39  mov     dword ptr [rbp+var_10], r13d
0x180007c3d  lea     rdx, [rbp+var_10]; unsigned __int8 *
0x180007c41  mov     r13d, 4
0x180007c47  mov     rcx, rbx; this
0x180007c4a  mov     r8d, r13d; unsigned int
0x180007c4d  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007c52  movzx   eax, byte ptr [rbp+arg_18]
0x180007c56  lea     rdx, [rbp+var_C]; unsigned __int8 *
0x180007c5a  mov     r8d, r13d; unsigned int
0x180007c5d  mov     dword ptr [rbp+var_C], eax
0x180007c60  mov     rcx, rbx; this
0x180007c63  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007c68  mov     r8d, r13d; unsigned int
0x180007c6b  lea     rdx, [rbp+var_1C]; unsigned __int8 *
0x180007c6f  mov     rcx, rbx; this
0x180007c72  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007c77  movzx   edx, si; unsigned __int16
0x180007c7a  mov     rcx, r14; this
0x180007c7d  call    ?mdGetBaseCatalogName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseCatalogName(ushort)
0x180007c82  xor     r15d, r15d
0x180007c85  test    rax, rax
0x180007c88  jz      short loc_180007CA0
0x180007c8a  movzx   edx, si; unsigned __int16
0x180007c8d  mov     rcx, r14; this
0x180007c90  call    ?mdGetBaseCatalogName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseCatalogName(ushort)
0x180007c95  mov     rdx, rax; unsigned __int16 *
0x180007c98  mov     rcx, rbx; this
0x180007c9b  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007ca0  movzx   edx, si; unsigned __int16
0x180007ca3  mov     rcx, r14; this
0x180007ca6  call    ?mdGetBaseSchemaName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseSchemaName(ushort)
0x180007cab  test    rax, rax
0x180007cae  jz      short loc_180007CC6
0x180007cb0  movzx   edx, si; unsigned __int16
0x180007cb3  mov     rcx, r14; this
0x180007cb6  call    ?mdGetBaseSchemaName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseSchemaName(ushort)
0x180007cbb  mov     rdx, rax; unsigned __int16 *
0x180007cbe  mov     rcx, rbx; this
0x180007cc1  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007cc6  mov     rcx, [rbx+0A0h]
0x180007ccd  test    rcx, rcx
0x180007cd0  jz      loc_180007DDA
0x180007cd6  imul    rdi, rsi, 25B0h
0x180007cdd  cmp     [rdi+rcx+18DCh], r15d
0x180007ce5  jnz     short loc_180007CFC
0x180007ce7  lea     rdx, [rcx+18D8h]
0x180007cee  mov     r8d, r13d; unsigned int
0x180007cf1  add     rdx, rdi; unsigned __int8 *
0x180007cf4  mov     rcx, rbx; this
0x180007cf7  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007cfc  mov     rax, [rbx+0A0h]
0x180007d03  cmp     [rax+rdi+18D4h], r15d
0x180007d0b  jnz     short loc_180007D22
0x180007d0d  lea     rdx, [rax+18D0h]
0x180007d14  mov     r8d, r13d; unsigned int
0x180007d17  add     rdx, rdi; unsigned __int8 *
0x180007d1a  mov     rcx, rbx; this
0x180007d1d  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007d22  mov     rax, [rbx+0A0h]
0x180007d29  cmp     [rax+rdi+18E4h], r15d
0x180007d31  jnz     short loc_180007D48
0x180007d33  lea     rdx, [rax+18E0h]
0x180007d3a  mov     r8d, r13d; unsigned int
0x180007d3d  add     rdx, rdi; unsigned __int8 *
0x180007d40  mov     rcx, rbx; this
0x180007d43  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007d48  mov     rax, [rbx+0A0h]
0x180007d4f  cmp     [rax+rdi+1900h], r15d
0x180007d57  jnz     short loc_180007D71
0x180007d59  lea     rdx, [rax+18E8h]
0x180007d60  mov     r8d, 18h; unsigned int
0x180007d66  add     rdx, rdi; unsigned __int8 *
0x180007d69  mov     rcx, rbx; this
0x180007d6c  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007d71  mov     rax, [rbx+0A0h]
0x180007d78  cmp     [rax+rdi+1D08h], r15d
0x180007d80  jnz     short loc_180007D94
0x180007d82  lea     rdx, [rax+1904h]
0x180007d89  mov     rcx, rbx; this
0x180007d8c  add     rdx, rdi; unsigned __int16 *
0x180007d8f  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007d94  mov     rax, [rbx+0A0h]
0x180007d9b  cmp     [rax+rdi+211Ch], r15d
0x180007da3  jnz     short loc_180007DB7
0x180007da5  lea     rdx, [rax+1D18h]
0x180007dac  mov     rcx, rbx; this
0x180007daf  add     rdx, rdi; unsigned __int16 *
0x180007db2  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007db7  mov     rax, [rbx+0A0h]
0x180007dbe  cmp     [rax+rdi+252Ch], r15d
0x180007dc6  jnz     short loc_180007DDA
0x180007dc8  lea     rdx, [rax+2128h]
0x180007dcf  mov     rcx, rbx; this
0x180007dd2  add     rdx, rdi; unsigned __int16 *
0x180007dd5  call    ?SaveString@GenADTG@@AEAAXPEBG@Z; GenADTG::SaveString(ushort const *)
0x180007dda  movzx   edx, si; unsigned __int16
0x180007ddd  mov     rcx, r14; this
0x180007de0  call    ?mdGetAutoIncrement@CMetaData@@QEAAFG@Z; CMetaData::mdGetAutoIncrement(ushort)
0x180007de5  mov     r8d, 2; unsigned int
0x180007deb  mov     word ptr [rbp+var_18], ax
0x180007def  mov     rcx, rbx; this
0x180007df2  lea     rdx, [rbp+var_18]; unsigned __int8 *
0x180007df6  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007dfb  mov     rcx, [rbx+0A0h]
0x180007e02  test    rcx, rcx
0x180007e05  jz      loc_180007EE4
0x180007e0b  imul    rdi, rsi, 25B0h
0x180007e12  cmp     [rdi+rcx+2544h], r15d
0x180007e1a  jnz     short loc_180007E34
0x180007e1c  lea     rdx, [rcx+2540h]
0x180007e23  mov     r8d, 2; unsigned int
0x180007e29  add     rdx, rdi; unsigned __int8 *
0x180007e2c  mov     rcx, rbx; this
  ... truncated ...
```
