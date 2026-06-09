# bond::CompactBinaryReader<bond::InputBuffer>::SkipType<uint &>(bond::_bond_enumerators::BondDataType::BondDataType,uint &)

- ea: `0x18000bfa0`
- end: `0x18000c0eb`
- name: `??$SkipType@AEAI@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXW4BondDataType@2_bond_enumerators@1@AEAI@Z`
- size: `331`
- prototype: `void __fastcall(bond::InputBuffer *this, int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000bec4`

## callees

- `0x18000bba8`
- `0x18000bc7c`
- `0x18000bd20`
- `0x18000bd4c`
- `0x18000bd78`
- `0x18000bde8`
- `0x18000be4c`
- `0x18000bec4`
- `0x18000bf24`
- `0x18000bfa0`
- `0x18001b55c`

## pseudocode

```c
void __fastcall bond::CompactBinaryReader<bond::InputBuffer>::SkipType<unsigned int &>(
        bond::InputBuffer *this,
        int a2,
        unsigned int *a3)
{
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  __int64 v11; // rsi
  __int64 v12; // rbx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  __int64 v20; // rsi
  __int64 v21; // rbx
  __int64 v22; // rsi
  __int64 v23; // rbx
  __int64 v24; // rsi
  __int64 v25; // rbx

  if ( a2 <= 10 )
  {
    if ( a2 == 10 )
    {
      bond::CompactBinaryReader<bond::InputBuffer>::SkipType<10>(this, *a3);
      return;
    }
    v4 = a2 - 2;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( v5 )
      {
        v6 = v5 - 1;
        if ( v6 )
        {
          v7 = v6 - 1;
          if ( v7 )
          {
            v8 = v7 - 1;
            if ( v8 )
            {
              v9 = v8 - 1;
              if ( !v9 )
              {
                bond::CompactBinaryReader<bond::InputBuffer>::SkipType<7>(this, *a3);
                return;
              }
              v10 = v9 - 1;
              if ( !v10 )
              {
                bond::CompactBinaryReader<bond::InputBuffer>::SkipType<8>(this, *a3);
                return;
              }
              if ( v10 == 1 )
              {
                v11 = *a3;
                v12 = 0;
                if ( *a3 )
                {
                  do
                  {
                    bond::CompactBinaryReader<bond::InputBuffer>::SkipStructV2(this);
                    ++v12;
                  }
                  while ( v12 < v11 );
                }
                return;
              }
LABEL_36:
              bond::UnknownDataTypeException(this);
            }
          }
        }
LABEL_28:
        bond::CompactBinaryReader<bond::InputBuffer>::SkipType<6>(this, *a3);
        return;
      }
    }
LABEL_29:
    bond::CompactBinaryReader<bond::InputBuffer>::SkipType<2>(this, *a3);
    return;
  }
  v13 = a2 - 11;
  if ( v13 && (v14 = v13 - 1) != 0 )
  {
    v15 = v14 - 1;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( !v16 )
        goto LABEL_29;
      v17 = v16 - 1;
      if ( !v17 )
        goto LABEL_28;
      v18 = v17 - 1;
      if ( !v18 )
        goto LABEL_28;
      v19 = v18 - 1;
      if ( !v19 )
        goto LABEL_28;
      if ( v19 != 1 )
        goto LABEL_36;
      v20 = *a3;
      v21 = 0;
      if ( *a3 )
      {
        do
        {
          bond::CompactBinaryReader<bond::InputBuffer>::SkipType<18>(this);
          ++v21;
        }
        while ( v21 < v20 );
      }
    }
    else
    {
      v22 = *a3;
      v23 = 0;
      if ( *a3 )
      {
        do
        {
          bond::CompactBinaryReader<bond::InputBuffer>::SkipType<13>(this);
          ++v23;
        }
        while ( v23 < v22 );
      }
    }
  }
  else
  {
    v24 = *a3;
    v25 = 0;
    if ( *a3 )
    {
      do
      {
        bond::CompactBinaryReader<bond::InputBuffer>::SkipType<12>(this);
        ++v25;
      }
      while ( v25 < v24 );
    }
  }
}

```

## disassembly

```asm
0x18000bfa0  mov     [rsp+arg_0], rbx
0x18000bfa5  mov     [rsp+arg_8], rsi
0x18000bfaa  push    rdi
0x18000bfab  sub     rsp, 20h
0x18000bfaf  mov     rdi, rcx
0x18000bfb2  cmp     edx, 0Ah
0x18000bfb5  jg      loc_18000C047
0x18000bfbb  jz      short loc_18000C03A
0x18000bfbd  sub     edx, 2
0x18000bfc0  jz      loc_18000C095
0x18000bfc6  sub     edx, 1
0x18000bfc9  jz      loc_18000C095
0x18000bfcf  sub     edx, 1
0x18000bfd2  jz      loc_18000C08B
0x18000bfd8  sub     edx, 1
0x18000bfdb  jz      loc_18000C08B
0x18000bfe1  sub     edx, 1
0x18000bfe4  jz      loc_18000C08B
0x18000bfea  sub     edx, 1
0x18000bfed  jz      short loc_18000C02D
0x18000bfef  sub     edx, 1
0x18000bff2  jz      short loc_18000C020
0x18000bff4  cmp     edx, 1
0x18000bff7  jnz     loc_18000C0E5
0x18000bffd  mov     esi, [r8]
0x18000c000  xor     ebx, ebx
0x18000c002  test    rsi, rsi
0x18000c005  jz      loc_18000C0D5
0x18000c00b  mov     rcx, rdi; this
0x18000c00e  call    ?SkipStructV2@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXXZ; bond::CompactBinaryReader<bond::InputBuffer>::SkipStructV2(void)
0x18000c013  inc     rbx
0x18000c016  cmp     rbx, rsi
0x18000c019  jl      short loc_18000C00B
0x18000c01b  jmp     loc_18000C0D5
0x18000c020  mov     edx, [r8]
0x18000c023  call    ??$SkipType@$07@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXI@Z; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<8>(uint)
0x18000c028  jmp     loc_18000C0D5
0x18000c02d  mov     edx, [r8]
0x18000c030  call    ??$SkipType@$06@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXI@Z; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<7>(uint)
0x18000c035  jmp     loc_18000C0D5
0x18000c03a  mov     edx, [r8]
0x18000c03d  call    ??$SkipType@$09@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXI@Z; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<10>(uint)
0x18000c042  jmp     loc_18000C0D5
0x18000c047  sub     edx, 0Bh
0x18000c04a  jz      short loc_18000C0BB
0x18000c04c  sub     edx, 1
0x18000c04f  jz      short loc_18000C0BB
0x18000c051  sub     edx, 1
0x18000c054  jz      short loc_18000C09F
0x18000c056  sub     edx, 1
0x18000c059  jz      short loc_18000C095
0x18000c05b  sub     edx, 1
0x18000c05e  jz      short loc_18000C08B
0x18000c060  sub     edx, 1
0x18000c063  jz      short loc_18000C08B
0x18000c065  sub     edx, 1
0x18000c068  jz      short loc_18000C08B
0x18000c06a  cmp     edx, 1
0x18000c06d  jnz     short loc_18000C0E5
0x18000c06f  mov     esi, [r8]
0x18000c072  xor     ebx, ebx
0x18000c074  test    rsi, rsi
0x18000c077  jz      short loc_18000C0D5
0x18000c079  mov     rcx, rdi; this
0x18000c07c  call    ??$SkipType@$0BC@@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXXZ; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<18>(void)
0x18000c081  inc     rbx
0x18000c084  cmp     rbx, rsi
0x18000c087  jl      short loc_18000C079
0x18000c089  jmp     short loc_18000C0D5
0x18000c08b  mov     edx, [r8]
0x18000c08e  call    ??$SkipType@$05@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXI@Z; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<6>(uint)
0x18000c093  jmp     short loc_18000C0D5
0x18000c095  mov     edx, [r8]
0x18000c098  call    ??$SkipType@$01@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXI@Z; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<2>(uint)
0x18000c09d  jmp     short loc_18000C0D5
0x18000c09f  mov     esi, [r8]
0x18000c0a2  xor     ebx, ebx
0x18000c0a4  test    rsi, rsi
0x18000c0a7  jz      short loc_18000C0D5
0x18000c0a9  mov     rcx, rdi; this
0x18000c0ac  call    ??$SkipType@$0N@@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXXZ; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<13>(void)
0x18000c0b1  inc     rbx
0x18000c0b4  cmp     rbx, rsi
0x18000c0b7  jl      short loc_18000C0A9
0x18000c0b9  jmp     short loc_18000C0D5
0x18000c0bb  mov     esi, [r8]
0x18000c0be  xor     ebx, ebx
0x18000c0c0  test    rsi, rsi
0x18000c0c3  jz      short loc_18000C0D5
0x18000c0c5  mov     rcx, rdi; this
0x18000c0c8  call    ??$SkipType@$0M@@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXXZ; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<12>(void)
0x18000c0cd  inc     rbx
0x18000c0d0  cmp     rbx, rsi
0x18000c0d3  jl      short loc_18000C0C5
0x18000c0d5  mov     rbx, [rsp+28h+arg_0]
0x18000c0da  mov     rsi, [rsp+28h+arg_8]
0x18000c0df  add     rsp, 20h
0x18000c0e3  pop     rdi
0x18000c0e4  retn
0x18000c0e5  call    ?UnknownDataTypeException@bond@@YAXXZ; bond::UnknownDataTypeException(void)
```
