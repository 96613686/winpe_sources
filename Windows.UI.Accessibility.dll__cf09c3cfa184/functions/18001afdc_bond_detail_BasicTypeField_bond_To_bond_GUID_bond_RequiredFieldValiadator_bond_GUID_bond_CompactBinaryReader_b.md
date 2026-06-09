# bond::detail::BasicTypeField<bond::To<bond::GUID,bond::RequiredFieldValiadator<bond::GUID>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<bond::GUID,bond::RequiredFieldValiadator<bond::GUID>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x18001afdc`
- end: `0x18001b290`
- name: `??$BasicTypeField@V?$To@UGUID@bond@@V?$RequiredFieldValiadator@UGUID@bond@@@2@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@UGUID@bond@@V?$RequiredFieldValiadator@UGUID@bond@@@2@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(int, int, int, int, bond::InputBuffer *)`
- caller_count: `4`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001cc94`
- `0x18001cce4`
- `0x18001cd34`
- `0x18001cd9c`

## callees

- `0x180010150`
- `0x1800101a4`
- `0x18001357c`
- `0x18001359c`
- `0x1800135bc`
- `0x1800135dc`
- `0x1800135fc`
- `0x18001361c`
- `0x18001363c`
- `0x18001ace8`
- `0x18001afdc`
- `0x18001c810`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall bond::detail::BasicTypeField<bond::To<bond::GUID,bond::RequiredFieldValiadator<bond::GUID>>,bond::CompactBinaryReader<bond::InputBuffer>>(
        unsigned __int16 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        bond::InputBuffer *a5)
{
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rdx
  _DWORD *v13; // rbx
  char v14; // bl
  int v16; // r8d
  int v17; // r8d
  int v18; // r8d
  int v19; // r8d
  int v20; // r8d
  bond::InputBuffer *v21; // [rsp+20h] [rbp-10h] BYREF
  char v22; // [rsp+28h] [rbp-8h]
  unsigned int v23; // [rsp+50h] [rbp+20h] BYREF

  if ( a3 > 8 )
  {
    v16 = a3 - 9;
    if ( v16 )
    {
      v17 = v16 - 5;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 && (v19 = v18 - 1) != 0 && (v20 = v19 - 1) != 0 )
        {
          if ( v20 == 1 )
          {
            v21 = a5;
            v22 = 1;
            bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
          }
        }
        else
        {
          v21 = a5;
          v22 = 1;
          bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
        }
      }
      else
      {
        v21 = a5;
        v22 = 1;
        bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
      }
    }
    else
    {
      v21 = a5;
      v22 = 1;
      bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
    }
    return 0;
  }
  if ( a3 == 8 )
  {
    v21 = a5;
    v22 = 1;
    bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
    return 0;
  }
  v5 = a3 - 2;
  if ( !v5 )
  {
    v21 = a5;
    v22 = 1;
    bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
    return 0;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v21 = a5;
    v22 = 1;
    v14 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, bond::InputBuffer **))bond::To<bond::GUID,bond::RequiredFieldValiadator<bond::GUID>>::AssignToField<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<4>,bond::reflection::FieldTemplate<3,bond::reflection::optional_field_modifier,bond::GUID,unsigned __int64,8,&private: static bond::Metadata const bond::GUID::Schema::s_Data4_metadata>,boost::mpl::l_item<boost::mpl::long_<3>,bond::reflection::FieldTemplate<2,bond::reflection::optional_field_modifier,bond::GUID,unsigned short,6,&private: static bond::Metadata const bond::GUID::Schema::s_Data3_metadata>,boost::mpl::l_item<boost::mpl::long_<2>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,bond::GUID,unsigned short,4,&private: static bond::Metadata const bond::GUID::Schema::s_Data2_metadata>,boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,bond::GUID,unsigned int,0,&private: static bond::Metadata const bond::GUID::Schema::s_Data1_metadata>,boost::mpl::l_end>>>>>,bond::value<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &,void>>)(
            a4,
            a2,
            a1,
            &v21);
    bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
    return v14;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( v9 == 1 )
        {
          v21 = a5;
          v22 = 1;
          bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
        }
        return 0;
      }
      v21 = a5;
      v22 = 1;
      if ( a1 == 3 )
      {
        v22 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(a5);
      }
    }
    else
    {
      v21 = a5;
      v22 = 1;
      if ( a1 == 3 )
      {
        v10 = *(_QWORD *)(a4 + 8);
        v23 = 0;
        v22 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned int>(a5);
        *(_QWORD *)(v10 + 8) = v23;
      }
      else if ( !a1 )
      {
        v22 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned int>(a5);
      }
    }
    goto LABEL_12;
  }
  v21 = a5;
  v22 = 1;
  if ( a1 == 3 )
  {
    v11 = *(_QWORD *)(a4 + 8);
    LOWORD(v23) = 0;
    v22 = 0;
    bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, &v23);
    *(_QWORD *)(v11 + 8) = (unsigned __int16)v23;
  }
  else
  {
    if ( a1 == 2 )
    {
      v12 = *(_QWORD *)(a4 + 8) + 6LL;
    }
    else
    {
      if ( a1 != 1 )
      {
        if ( !a1 )
        {
          v13 = *(_DWORD **)(a4 + 8);
          LOWORD(v23) = 0;
          v22 = 0;
          bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, &v23);
          *v13 = (unsigned __int16)v23;
        }
        goto LABEL_12;
      }
      v12 = *(_QWORD *)(a4 + 8) + 4LL;
    }
    v22 = 0;
    bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, v12);
  }
LABEL_12:
  bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
  return 0;
}

```

## disassembly

```asm
0x18001afdc  mov     [rsp-8+arg_0], rbx
0x18001afe1  push    rbp
0x18001afe2  mov     rbp, rsp
0x18001afe5  sub     rsp, 30h
0x18001afe9  mov     r10, r9
0x18001afec  cmp     r8d, 8
0x18001aff0  jg      loc_18001B1CF
0x18001aff6  jz      loc_18001B1B5
0x18001affc  mov     eax, 2
0x18001b001  sub     r8d, eax
0x18001b004  jz      loc_18001B19B
0x18001b00a  sub     r8d, 1
0x18001b00e  jz      loc_18001B16D
0x18001b014  sub     r8d, 1
0x18001b018  jz      loc_18001B0DA
0x18001b01e  sub     r8d, 1
0x18001b022  jz      short loc_18001B084
0x18001b024  sub     r8d, 1
0x18001b028  jz      short loc_18001B04E
0x18001b02a  cmp     r8d, 1
0x18001b02e  jnz     loc_18001B283
0x18001b034  mov     rax, [rbp+arg_20]
0x18001b038  mov     [rbp+var_10], rax
0x18001b03c  mov     [rbp+var_8], r8b
0x18001b040  lea     rcx, [rbp+var_10]
0x18001b044  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b049  jmp     loc_18001B283
0x18001b04e  mov     r8, [rbp+arg_20]
0x18001b052  mov     [rbp+var_10], r8
0x18001b056  mov     [rbp+var_8], 1
0x18001b05a  cmp     cx, 3
0x18001b05e  jnz     short loc_18001B076
0x18001b060  xor     eax, eax
0x18001b062  mov     [rbp+var_8], al
0x18001b065  mov     rdx, [r9+8]
0x18001b069  add     rdx, 8
0x18001b06d  mov     rcx, r8; this
0x18001b070  call    ??$ReadVariableUnsigned@_K@InputBuffer@bond@@QEAAXAEA_K@Z; bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(unsigned __int64 &)
0x18001b075  nop
0x18001b076  lea     rcx, [rbp+var_10]
0x18001b07a  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b07f  jmp     loc_18001B283
0x18001b084  mov     r8, [rbp+arg_20]
0x18001b088  mov     [rbp+var_10], r8
0x18001b08c  mov     [rbp+var_8], 1
0x18001b090  xor     eax, eax
0x18001b092  cmp     cx, 3
0x18001b096  jnz     short loc_18001B0B7
0x18001b098  mov     rbx, [r9+8]
0x18001b09c  mov     [rbp+arg_10], eax
0x18001b09f  mov     [rbp+var_8], al
0x18001b0a2  lea     rdx, [rbp+arg_10]
0x18001b0a6  mov     rcx, r8; this
0x18001b0a9  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x18001b0ae  mov     eax, [rbp+arg_10]
0x18001b0b1  mov     [rbx+8], rax
0x18001b0b5  jmp     short loc_18001B0CC
0x18001b0b7  test    cx, cx
0x18001b0ba  jnz     short loc_18001B0CC
0x18001b0bc  mov     [rbp+var_8], al
0x18001b0bf  mov     rdx, [r9+8]
0x18001b0c3  mov     rcx, r8; this
0x18001b0c6  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x18001b0cb  nop
0x18001b0cc  lea     rcx, [rbp+var_10]
0x18001b0d0  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b0d5  jmp     loc_18001B283
0x18001b0da  mov     r8, [rbp+arg_20]
0x18001b0de  mov     [rbp+var_10], r8
0x18001b0e2  mov     [rbp+var_8], 1
0x18001b0e6  cmp     cx, 3
0x18001b0ea  jnz     short loc_18001B10F
0x18001b0ec  mov     rbx, [r9+8]
0x18001b0f0  xor     eax, eax
0x18001b0f2  mov     word ptr [rbp+arg_10], ax
0x18001b0f6  mov     [rbp+var_8], al
0x18001b0f9  lea     rdx, [rbp+arg_10]
0x18001b0fd  mov     rcx, r8
0x18001b100  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18001b105  movzx   eax, word ptr [rbp+arg_10]
0x18001b109  mov     [rbx+8], rax
0x18001b10d  jmp     short loc_18001B15F
0x18001b10f  cmp     cx, ax
0x18001b112  jnz     short loc_18001B120
0x18001b114  xor     eax, eax
0x18001b116  mov     rdx, [r9+8]
0x18001b11a  add     rdx, 6
0x18001b11e  jmp     short loc_18001B130
0x18001b120  xor     eax, eax
0x18001b122  cmp     cx, 1
0x18001b126  jnz     short loc_18001B13D
0x18001b128  mov     rdx, [r9+8]
0x18001b12c  add     rdx, 4
0x18001b130  mov     [rbp+var_8], al
0x18001b133  mov     rcx, r8
0x18001b136  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18001b13b  jmp     short loc_18001B15F
0x18001b13d  test    cx, cx
0x18001b140  jnz     short loc_18001B15F
0x18001b142  mov     rbx, [r9+8]
0x18001b146  mov     word ptr [rbp+arg_10], ax
0x18001b14a  mov     [rbp+var_8], al
0x18001b14d  lea     rdx, [rbp+arg_10]
0x18001b151  mov     rcx, r8
0x18001b154  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18001b159  movzx   eax, word ptr [rbp+arg_10]
0x18001b15d  mov     [rbx], eax
0x18001b15f  lea     rcx, [rbp+var_10]
0x18001b163  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b168  jmp     loc_18001B283
0x18001b16d  mov     rax, [rbp+arg_20]
0x18001b171  mov     [rbp+var_10], rax
0x18001b175  mov     [rbp+var_8], 1
0x18001b179  lea     r9, [rbp+var_10]
0x18001b17d  movzx   r8d, cx
0x18001b181  mov     rcx, r10
0x18001b184  call    ??$AssignToField@U?$l_iter@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UGUID@3@_K$07$1?s_Data4_metadata@Schema@GUID@bond@@0UMetadata@3@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UGUID@3@G$05$1?s_Data3_metadata@Schema@GUID@bond@@0UMetadata@3@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UGUID@3@G$03$1?s_Data2_metadata@Schema@GUID@bond@@0UMetadata@3@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UGUID@3@I$0A@$1?s_Data1_metadata@Schema@GUID@bond@@0UMetadata@3@B@reflection@bond@@Ul_end@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@V?$value@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@?$To@UGUID@bond@@V?$RequiredFieldValiadator@UGUID@bond@@@2@@bond@@AEBA_NAEBU?$l_iter@U?$l_item@U?$long_@$03@mpl@boost@@U?$FieldTemplate@$02Uoptional_field_modifier@reflection@bond@@UGUID@3@_K$07$1?s_Data4_metadata@Schema@GUID@bond@@0UMetadata@3@B@reflection@bond@@U?$l_item@U?$long_@$02@mpl@boost@@U?$FieldTemplate@$01Uoptional_field_modifier@reflection@bond@@UGUID@3@G$05$1?s_Data3_metadata@Schema@GUID@bond@@0UMetadata@3@B@reflection@bond@@U?$l_item@U?$long_@$01@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UGUID@3@G$03$1?s_Data2_metadata@Schema@GUID@bond@@0UMetadata@3@B@reflection@bond@@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UGUID@3@I$0A@$1?s_Data1_metadata@Schema@GUID@bond@@0UMetadata@3@B@reflection@bond@@Ul_end@23@@23@@23@@23@@mpl@boost@@@mpl@boost@@GAEBV?$value@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@1@@Z
0x18001b189  mov     bl, al
0x18001b18b  lea     rcx, [rbp+var_10]
0x18001b18f  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b194  mov     al, bl
0x18001b196  jmp     loc_18001B285
0x18001b19b  mov     rax, [rbp+arg_20]
0x18001b19f  mov     [rbp+var_10], rax
0x18001b1a3  mov     [rbp+var_8], 1
0x18001b1a7  lea     rcx, [rbp+var_10]
0x18001b1ab  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b1b0  jmp     loc_18001B283
0x18001b1b5  mov     rax, [rbp+arg_20]
0x18001b1b9  mov     [rbp+var_10], rax
0x18001b1bd  mov     [rbp+var_8], 1
0x18001b1c1  lea     rcx, [rbp+var_10]
0x18001b1c5  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b1ca  jmp     loc_18001B283
0x18001b1cf  sub     r8d, 9
0x18001b1d3  jz      loc_18001B26E
0x18001b1d9  sub     r8d, 5
0x18001b1dd  jz      short loc_18001B257
0x18001b1df  sub     r8d, 1
0x18001b1e3  jz      short loc_18001B240
0x18001b1e5  sub     r8d, 1
0x18001b1e9  jz      short loc_18001B229
0x18001b1eb  sub     r8d, 1
0x18001b1ef  jz      short loc_18001B212
0x18001b1f1  cmp     r8d, 1
0x18001b1f5  jnz     loc_18001B283
0x18001b1fb  mov     rax, [rbp+arg_20]
0x18001b1ff  mov     [rbp+var_10], rax
0x18001b203  mov     [rbp+var_8], r8b
0x18001b207  lea     rcx, [rbp+var_10]
0x18001b20b  call    ??1?$value_common@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b210  jmp     short loc_18001B283
0x18001b212  mov     rax, [rbp+arg_20]
0x18001b216  mov     [rbp+var_10], rax
0x18001b21a  mov     [rbp+var_8], 1
0x18001b21e  lea     rcx, [rbp+var_10]
0x18001b222  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b227  jmp     short loc_18001B283
0x18001b229  mov     rax, [rbp+arg_20]
0x18001b22d  mov     [rbp+var_10], rax
0x18001b231  mov     [rbp+var_8], 1
0x18001b235  lea     rcx, [rbp+var_10]
0x18001b239  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b23e  jmp     short loc_18001B283
0x18001b240  mov     rax, [rbp+arg_20]
0x18001b244  mov     [rbp+var_10], rax
0x18001b248  mov     [rbp+var_8], 1
0x18001b24c  lea     rcx, [rbp+var_10]
0x18001b250  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b255  jmp     short loc_18001B283
0x18001b257  mov     rax, [rbp+arg_20]
0x18001b25b  mov     [rbp+var_10], rax
0x18001b25f  mov     [rbp+var_8], 1
0x18001b263  lea     rcx, [rbp+var_10]
0x18001b267  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b26c  jmp     short loc_18001B283
0x18001b26e  mov     rax, [rbp+arg_20]
0x18001b272  mov     [rbp+var_10], rax
0x18001b276  mov     [rbp+var_8], 1
0x18001b27a  lea     rcx, [rbp+var_10]
0x18001b27e  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b283  xor     al, al
0x18001b285  mov     rbx, [rsp+30h+arg_0]
0x18001b28a  add     rsp, 30h
0x18001b28e  pop     rbp
0x18001b28f  retn
```
