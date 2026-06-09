# bond::CompactBinaryReader<bond::InputBuffer>::SkipType<>(bond::_bond_enumerators::BondDataType::BondDataType)

- ea: `0x18000ba24`
- end: `0x18000bb9f`
- name: `??$SkipType@$$V@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXW4BondDataType@2_bond_enumerators@1@@Z`
- size: `379`
- prototype: `unsigned __int64 __fastcall(bond::InputBuffer *this, int)`
- caller_count: `5`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000a7a4`
- `0x18000aa0c`
- `0x18000bf24`
- `0x18000c12c`
- `0x180019834`

## callees

- `0x18000a47c`
- `0x18000ba24`
- `0x18000bba8`
- `0x18000bd20`
- `0x18000bd4c`
- `0x18000bd78`
- `0x18000be4c`
- `0x18000bec4`
- `0x18000bf24`
- `0x1800172ac`
- `0x180019834`
- `0x18001b55c`

## pseudocode

```c
unsigned __int64 __fastcall bond::CompactBinaryReader<bond::InputBuffer>::SkipType<>(bond::InputBuffer *this, int a2)
{
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  unsigned __int64 result; // rax
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  __int64 v21; // rdx
  unsigned __int64 v22; // [rsp+40h] [rbp+18h] BYREF
  __int64 v23; // [rsp+48h] [rbp+20h] BYREF

  if ( a2 > 10 )
  {
    v11 = a2 - 11;
    if ( !v11 )
      return bond::CompactBinaryReader<bond::InputBuffer>::SkipType<12>(this);
    v12 = v11 - 1;
    if ( !v12 )
      return bond::CompactBinaryReader<bond::InputBuffer>::SkipType<12>(this);
    v13 = v12 - 1;
    if ( !v13 )
      return bond::CompactBinaryReader<bond::InputBuffer>::SkipType<13>(this);
    v14 = v13 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          v17 = v16 - 1;
          if ( v17 )
          {
            if ( v17 != 1 )
              goto LABEL_33;
            return bond::CompactBinaryReader<bond::InputBuffer>::SkipType<18>(this);
          }
        }
      }
LABEL_25:
      v18 = *((unsigned int *)this + 6);
      v19 = *((unsigned int *)this + 4);
      v22 = 0;
      if ( v19 <= v18 + 9 )
        return bond::GenericReadVariableUnsigned<bond::InputBuffer,unsigned __int64>(this, &v22);
      v20 = *(char *)(v18 + *(_QWORD *)this);
      v21 = *(_QWORD *)this + 1LL + v18;
      result = v20 & 0x7F;
      v23 = v21;
      v22 = result;
      if ( v20 >= 0x80 )
      {
        result = bond::input_buffer::VariableUnsignedUnchecked<unsigned __int64,7>::Read(&v23, &v22);
        LODWORD(v21) = v23;
      }
      *((_DWORD *)this + 6) = v21 - *(_DWORD *)this;
      return result;
    }
    return bond::CompactBinaryReader<bond::InputBuffer>::SkipType<2>(this);
  }
  if ( a2 == 10 )
  {
    if ( *((_WORD *)this + 16) == 2 )
      return bond::CompactBinaryReader<bond::InputBuffer>::SkipStructV2(this);
    return bond::CompactBinaryReader<bond::InputBuffer>::SkipStructV1(this);
  }
  v3 = a2 - 2;
  if ( !v3 )
    return bond::CompactBinaryReader<bond::InputBuffer>::SkipType<2>(this);
  v4 = v3 - 1;
  if ( !v4 )
    return bond::CompactBinaryReader<bond::InputBuffer>::SkipType<2>(this);
  v5 = v4 - 1;
  if ( !v5 )
    goto LABEL_25;
  v6 = v5 - 1;
  if ( !v6 )
    goto LABEL_25;
  v7 = v6 - 1;
  if ( !v7 )
    goto LABEL_25;
  v8 = v7 - 1;
  if ( !v8 )
    return bond::CompactBinaryReader<bond::InputBuffer>::SkipType<7>(this);
  v9 = v8 - 1;
  if ( v9 )
  {
    if ( v9 == 1 )
      return bond::CompactBinaryReader<bond::InputBuffer>::SkipStructV2(this);
LABEL_33:
    bond::UnknownDataTypeException(this);
  }
  return bond::CompactBinaryReader<bond::InputBuffer>::SkipType<8>(this);
}

```

## disassembly

```asm
0x18000ba24  push    rbx
0x18000ba26  sub     rsp, 20h
0x18000ba2a  mov     rbx, rcx
0x18000ba2d  cmp     edx, 0Ah
0x18000ba30  jg      loc_18000BABF
0x18000ba36  jz      short loc_18000BAA0
0x18000ba38  sub     edx, 2
0x18000ba3b  jz      loc_18000BB76
0x18000ba41  sub     edx, 1
0x18000ba44  jz      loc_18000BB76
0x18000ba4a  sub     edx, 1
0x18000ba4d  jz      loc_18000BB05
0x18000ba53  sub     edx, 1
0x18000ba56  jz      loc_18000BB05
0x18000ba5c  sub     edx, 1
0x18000ba5f  jz      loc_18000BB05
0x18000ba65  sub     edx, 1
0x18000ba68  jz      short loc_18000BA91
0x18000ba6a  sub     edx, 1
0x18000ba6d  jz      short loc_18000BA82
0x18000ba6f  cmp     edx, 1
0x18000ba72  jnz     loc_18000BB99
0x18000ba78  add     rsp, 20h
0x18000ba7c  pop     rbx
0x18000ba7d  jmp     ?SkipStructV2@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXXZ; bond::CompactBinaryReader<bond::InputBuffer>::SkipStructV2(void)
0x18000ba82  mov     edx, 1
0x18000ba87  add     rsp, 20h
0x18000ba8b  pop     rbx
0x18000ba8c  jmp     ??$SkipType@$07@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXI@Z; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<8>(uint)
0x18000ba91  mov     edx, 1
0x18000ba96  add     rsp, 20h
0x18000ba9a  pop     rbx
0x18000ba9b  jmp     ??$SkipType@$06@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXI@Z; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<7>(uint)
0x18000baa0  mov     eax, 2
0x18000baa5  cmp     ax, [rcx+20h]
0x18000baa9  jnz     short loc_18000BAB5
0x18000baab  add     rsp, 20h
0x18000baaf  pop     rbx
0x18000bab0  jmp     ?SkipStructV2@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXXZ; bond::CompactBinaryReader<bond::InputBuffer>::SkipStructV2(void)
0x18000bab5  add     rsp, 20h
0x18000bab9  pop     rbx
0x18000baba  jmp     ?SkipStructV1@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXXZ; bond::CompactBinaryReader<bond::InputBuffer>::SkipStructV1(void)
0x18000babf  sub     edx, 0Bh
0x18000bac2  jz      loc_18000BB8F
0x18000bac8  sub     edx, 1
0x18000bacb  jz      loc_18000BB8F
0x18000bad1  sub     edx, 1
0x18000bad4  jz      loc_18000BB85
0x18000bada  sub     edx, 1
0x18000badd  jz      loc_18000BB76
0x18000bae3  sub     edx, 1
0x18000bae6  jz      short loc_18000BB05
0x18000bae8  sub     edx, 1
0x18000baeb  jz      short loc_18000BB05
0x18000baed  sub     edx, 1
0x18000baf0  jz      short loc_18000BB05
0x18000baf2  cmp     edx, 1
0x18000baf5  jnz     loc_18000BB99
0x18000bafb  add     rsp, 20h
0x18000baff  pop     rbx
0x18000bb00  jmp     ??$SkipType@$0BC@@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXXZ; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<18>(void)
0x18000bb05  mov     edx, [rcx+18h]
0x18000bb08  mov     ecx, [rcx+10h]
0x18000bb0b  mov     [rsp+28h+arg_10], 0
0x18000bb14  lea     rax, [rdx+9]
0x18000bb18  cmp     rcx, rax
0x18000bb1b  jbe     short loc_18000BB63
0x18000bb1d  mov     rax, [rbx]
0x18000bb20  movsx   rcx, byte ptr [rdx+rax]
0x18000bb25  inc     rax
0x18000bb28  add     rdx, rax
0x18000bb2b  mov     rax, rcx
0x18000bb2e  and     eax, 7Fh
0x18000bb31  mov     [rsp+28h+arg_18], rdx
0x18000bb36  mov     [rsp+28h+arg_10], rax
0x18000bb3b  cmp     rcx, 80h
0x18000bb42  jb      short loc_18000BB58
0x18000bb44  lea     rdx, [rsp+28h+arg_10]
0x18000bb49  lea     rcx, [rsp+28h+arg_18]
0x18000bb4e  call    ?Read@?$VariableUnsignedUnchecked@_K$06@input_buffer@bond@@SAXAEAPEBDAEA_K@Z; bond::input_buffer::VariableUnsignedUnchecked<unsigned __int64,7>::Read(char const * &,unsigned __int64 &)
0x18000bb53  mov     rdx, [rsp+28h+arg_18]
0x18000bb58  sub     edx, [rbx]
0x18000bb5a  mov     [rbx+18h], edx
0x18000bb5d  add     rsp, 20h
0x18000bb61  pop     rbx
0x18000bb62  retn
0x18000bb63  lea     rdx, [rsp+28h+arg_10]
0x18000bb68  mov     rcx, rbx; this
0x18000bb6b  call    ??$GenericReadVariableUnsigned@VInputBuffer@bond@@_K@bond@@YAXAEAVInputBuffer@0@AEA_K@Z; bond::GenericReadVariableUnsigned<bond::InputBuffer,unsigned __int64>(bond::InputBuffer &,unsigned __int64 &)
0x18000bb70  add     rsp, 20h
0x18000bb74  pop     rbx
0x18000bb75  retn
0x18000bb76  mov     edx, 1
0x18000bb7b  add     rsp, 20h
0x18000bb7f  pop     rbx
0x18000bb80  jmp     ??$SkipType@$01@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXI@Z; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<2>(uint)
0x18000bb85  add     rsp, 20h
0x18000bb89  pop     rbx
0x18000bb8a  jmp     ??$SkipType@$0N@@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXXZ; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<13>(void)
0x18000bb8f  add     rsp, 20h
0x18000bb93  pop     rbx
0x18000bb94  jmp     ??$SkipType@$0M@@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXXZ; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<12>(void)
0x18000bb99  call    ?UnknownDataTypeException@bond@@YAXXZ; bond::UnknownDataTypeException(void)
```
